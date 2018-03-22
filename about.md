---
layout: post
title: About
permalink: /about/
author: Himanshu  
---

[Go](https://golang.org/) is a wonderful language, I had my aha moment with the language
when I wrote a "Hello World" of http server and ran
[ApacheBench tool](https://httpd.apache.org/docs/2.4/programs/ab.html) (ab).
The aha moment was seeing that a simple program can handle thousands of requests per second.

{% highlight go %}
package main

import (
  "log"
  "net/http"
)

func main() {
  http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
     w.Write([]byte(`
        <html>
          <head>
            <title>Hello World</title>
          </head>
          <body>
            Hello World!
          </body>
        </html>
    `))
  })
  if err := http.ListenAndServe(":8080", nil); err != nil {
    log.Fatal("ListenAndServe:", err)
  }
}
{% endhighlight %}

To run the program (saved in web.go file) just type `go run web.go`.
And open `http://localhost:8080` in your favourite browser.

 My eyes popped out when I saw the stats on running apache benchmark for 10K
 requests with 100 concurrent requests for the code above:
`ab -n 10000 -c 100 http://localhost:8080/`
{% highlight bash %}
Concurrency Level:      100
Time taken for tests:   1.581 seconds
Complete requests:      10000
Failed requests:        0
Total transferred:      2070000 bytes
HTML transferred:       910000 bytes
Requests per second:    6327.02 [#/sec] (mean)
Time per request:       15.805 [ms] (mean)
Time per request:       0.158 [ms] (mean, across all concurrent requests)
Transfer rate:          1279.00 [Kbytes/sec] received
{% endhighlight %}

I ran this on MacBook Pro mid-2015 model.

And I'm just getting started, the posts here won't be introduction to Programming
instead a quick comprehensive showcase of Go
which you can then compare to other languages that you already know.

I hope you find these posts useful!

Go!

If you are feeling adventurous and want to add something please feel free
to send PR @ [64bit.github.io](https://github.com/64bit/64bit.github.io)
