---
layout: post
title: "CSV -> MongoDB"
date: 2015-06-29 00:01
cover: cover.jpg
comments: true
categories: [mongodb]
---
I'm still listening to the Chemical Brothers Glastonbury set.

I'm also dabbling with MongoDB and the [OFSTED schools dataset](https://www.gov.uk/government/organisations/ofsted/about/statistics).

Inspired by [Locrating](http://locrating.com), an urge to learn MongoDB and a bit of spare time, I thought I'd take the CSV file describing most (all?) schools in England (and Wales?) and import it into MongoDB.  To be clear, this isn't a Big Data-style dataset, coming in at around 20,000 records, but I'm already pretty familiar with more traditional SQL DBs, so what the hell...

The first snippet of interest is a Python script to take the CSV file and import it into a new collection in MongoDB.  It's pretty simple, but with a little modification, could be used more generally.

{% highlight python3 linenos %}
#! python

import csv
from datetime import datetime
from pymongo import MongoClient

def insert_parsed_kvp(src_dict, dest_dict, src_id, dest_id, parse_func):
	dest_dict[dest_id] = parse_func(src_dict[src_id])

def parse_date(date_str):
	return datetime.strptime(str(date_str), r'%d/%m/%Y')

csvPath = r'assets/07_1409_Schools_Most_Recent_Mar14_Final.csv'

client = MongoClient()
db = client.db

fields = {
	'URN': { 'parse_func': int, 'alt_id': 'urn' },
	'LAESTAB': { 'parse_func': int, 'alt_id': 'laestab' },
	'School name': { 'parse_func': str, 'alt_id': 'name' },
	'Region': { 'parse_func': str, 'alt_id': 'region' },
	'Local Authority (education)': { 'parse_func': str, 'alt_id': 'local_authority' },
	'Parliamentary constituency': { 'parse_func': str, 'alt_id': 'constituency' },
	'Postcode': { 'parse_func': str, 'alt_id': 'postcode' },
	'Type of establishment': { 'parse_func': str, 'alt_id': 'establishment_type' },
	'Phase': { 'parse_func': str, 'alt_id': 'phase' },
	'Inspection number': { 'parse_func': int, 'alt_id': 'inspection_number' },
	'Inspection start date': { 'parse_func': parse_date, 'alt_id': 'inspection_date_start' },
	'Inspection end date': { 'parse_func': parse_date, 'alt_id': 'inspection_date_end' },
	'Inspection type': { 'parse_func': str, 'alt_id': 'inspection_type' },
	'Predecessor URN': { 'parse_func': str, 'alt_id': 'prev_urn' },
	'Overall effectiveness: how good is the school': { 'parse_func': int, 'alt_id': 'effectiveness' },
	'How well do learners achieve': { 'parse_func': int, 'alt_id': 'learner_achievement' },
	'Achievement of pupils': { 'parse_func': int, 'alt_id': 'pupil_achievement' },
	'Behaviour and safety of pupils': { 'parse_func': int, 'alt_id': 'behaviour' },
	'Quality of teaching': { 'parse_func': int, 'alt_id': 'teaching_quality' },
	'Leadership and management': { 'parse_func': int, 'alt_id': 'leadership' },
	'Category of concern': { 'parse_func': str, 'alt_id': 'concern_category' },
	'Warning notices in 2013/14 academic year': { 'parse_func': int, 'alt_id': 'warning_13_14' },
}

with open (csvPath, 'rb') as csvfile:
	reader = csv.DictReader(csvfile, delimiter=',')

	records_for_insert = []

	for row in reader:
		record = {}
		for field_id, field_desc in fields.iteritems():
			db_id = field_desc['alt_id']
			parse_func = field_desc['parse_func']
			insert_parsed_kvp(row, record, field_id, db_id, parse_func)

		records_for_insert.append(record)

	schools = db.schools
	schools.insert_many(records_for_insert)
	print('Inserted records for '+str(schools.count())+' schools')

	client.close()
{% endhighlight %}

