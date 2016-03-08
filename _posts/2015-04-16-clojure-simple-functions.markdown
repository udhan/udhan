---
layout: post
title:  "Clojure - Simple Functions"
date:   2015-04-16 01:10:56 -0800
categories: en
tags: clojure lisp programming
---
Functions are first class in clojure. Lets write a function in clojure which implements functionality similar to https://github.com/holman/bubs

**Problem:** Write a simple clojure function which takes a string as an input and returns bubbled version of it.

e.g. Mithun => Ⓜⓘⓣⓗⓤⓝ

Lets try to find out code difference between A and Ⓐ

    hello.core> (- (int \Ⓐ) (int \A))
	9333
    hello.core> (- (int \ⓐ) (int \a))
	9327

We got both numbers. Lets write simple function to do the conversion.

{% highlight clojure %}

(defn bub-inc [c]
  (if (Character/isUpperCase c)
    9333 9327))

(defn bub [c]
  (char (+ (int c) (bub-inc c))))

(defn bubs [s]
  (apply str (map bub s)))
  
{% endhighlight %}

Function named bubs achieves what problem statement stated. Following is summary of what we understand from the bubs program.
 
 - In clojure functions are defined using `defn`
 - Vector is used to accept parameters
 - `map` function: runs a given function on each element of collection.
 - Writing smaller functions is preferred/idomatic
 - You can use `char` to convert integer value to its character representation and `int` function to convert a character to its integer value.
