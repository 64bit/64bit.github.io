---
layout: post
title:  Introduction!
date:   2018-03-22 12:28:39 -0800
categories: go programming introduction
author: Himanshu
---

Go is a wonderful language! It combines great ideas from various programming
languages: pointers like C, garbage collection like Python, goroutines for
concurrency like Erlang processes, channels for communicating between goroutines like Erlang message passing, and no classes!

Lets see a complete Go program :

{% highlight go %}
package main

import "fmt"

func main() {
    // print a line
    fmt.Println("Hello World!")
}

{% endhighlight %}
