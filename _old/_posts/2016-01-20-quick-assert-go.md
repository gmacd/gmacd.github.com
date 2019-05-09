---
layout: post
title: "Quick Assert in Go"
date: 2016-01-20 07:07
cover: cover.jpg
comments: true
categories: [go]
---
One of the great things about Go is the integrated testing and benchmarking framework.  Unfortunately, using it is a little verbose.

I've spent a lot of time in the .Net world, using Nunit and more recently Fluent Assertions.  I missed the classic Nunit-style 'Assert.Equal(...)' and tried out the [testify](https://github.com/stretchr/testify) package.  It seemed a little big for what I needed, but other than an error message during install<sup>[1](#footnote1)</sup> it worked.

On the other hand, it's another big-ish dependency required for only a single function.

So wrote my own version:

{% highlight go linenos %}
package test

import (
	"fmt"
	"testing"
)

func Equal(t *testing.T, expected, actual interface{}, msg string, args ...interface{}) {
	if expected != actual {
		msg := fmt.Sprintf(msg, args...)
		t.Errorf("%v: Expected %v but found %v", msg, expected, actual)
	}
}
{% endhighlight %}

(I didn't reference testify's implementation.  I imagine it's similar as it's not a very complex problem)

There's lots more in testify (e.g. mocking), but this is all I need for now, and I don't imagine I'll need much more in the future, so I'll be sticking to this rather than pulling in another dependency.

<a name="footnote1">1</a>
<pre>go install vendor/golang.org/x/net/http2/hpack: open /usr/local/go/pkg/darwin_amd64/vendor/golang.org/x/net/http2/hpack.a: permission denied</pre>