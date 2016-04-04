---
layout: post
title:  "Introduction to Clojure"
date:   2016-03-27 22:00:56 -0800
categories: en
tags: clojure programming lisp
lang: en
ref: clojure-introduction
---
This is an introduction to clojure, a lisp dialect which runs on hosted platforms such as JVM. There is an implementation of clojure which compiles to javascript and clojure CLR which targets .Net environment as well. 

## Why clojure

 As it goes for any other language, clojure has its advantages and also has its share of weaknesses. Some may appreciate the elegance and succinctness of the Clojure others may not like its prefix s-expression syntax. Lets go through some of the top reasons why one might want to consider clojure over other languages.

If you have some experience in dynamic languages such as python or javascript most probably java feels too verbose and restrictive programming language. However when it comes to the JVM, it is one of the best runtime out there. Its ubiquitous availability, maturity and speed makes JVM extremely attractive environment.

Clojure is designed for JVM. Therefore provides excellent integration with it and takes full advantage of the platform. We can use any java library in clojure!

Further, clojure is designed for concurrency. With processor advancements now a days mostly focusing on adding more cores, it is important to take advantage of them. Clojure makes it easier to handle concurrency in applications by providing primitives for it.

Another decision which supports concurrency in clojure is the fact that all data structures in clojure are immutable. Yes! like immutable strings that we have in most programming languages. At the same time, they are quite performant and efficient in their implementation. This sounds contradictory but it is true.

With that, lets dive into clojure ecosystem and see how to get started!

## Getting started with clojure

You can download clojure just as single jar with all its glory! Go to http://clojure.org/community/download and download the clojure. Extract zip file and you will find an clojure-x.x.x.jar.

### Hello world

Run it as follows

    java -cp clojure-x.x.x.jar clojure.main

It will open an REPL

    user=> (println "Hello world")
    Hello world
    nil
    
Thats it! You just wrote your first code in clojure

### Understanding Basics

Lets explore more and try to understand what just happened.

By running jar we start Read-eval-print loop or REPL. It is interactive environment for clojure where you can write clojure code and it is read, evaluated and result is printed immediately.

    user=> (+ 1 2 3)
    6
    
For the most part syntax of the clojure is just that. It is called s-expressions. If you don't know already, this is good time to refresh little bit about [s-expressions](https://en.wikipedia.org/wiki/S-expression) as well as [prefix notation](https://en.wikipedia.org/wiki/Polish_notation).

Now that you are equipped with knowledge of clojure syntax, lets explore some of the data structures provided by clojure.

#### Vectors

    user=> (vector 1 2 3)
    [1 2 3]
    
    user=> [1 2 3]
    [1 2 3]
    
    ;; Accessing first element
    user=> (first [1 2 3])
    1
    
    ;; Accessing elements other than first
    user=> (rest [1 2 3])
    (2 3)
    
    ;; Get element at index
    user=> (get [1 2 3] 1)
    2

    
#### Lists

    user=> (list 1 2 3)
    (1 2 3)
    
    user=> '(1 2 3)
    (1 2 3)
    
    ;; Accessing first element
    user=> (first '(1 2 3))
    1
    
    ;; Accessing elements other than first
    user=> (rest '(1 2 3))
    (2 3)
    
#### Keyword

    ;; Resolves to self
    user=> :a
    :a
    
    ;; String representation of keyword
    user=> (name :a)
    "a"
    
    ;; Create keyword from string
    user=> (keyword "alpha")
    :alpha
    
#### Hashmap

    use=> (hash-map :a 1 :b 2 :c 3)
    {:c 3, :b 2, :a 1}
    
    user=> {:a 1 :b 2 :c 3}
    {:a 1, :b 2, :c 3}
    
    ;; Using keywords to get retrieve item in hash-map
    user=> (:a {:a 1 :b 2 :c 3})
    1
    
    ;; hash-map as function
    user=> ({:a 1 :b 2 :c 3} :b)
    2


Thats lots of things to learn! However clojure is consistent not just with its syntax but also with data structures. As you can see first and rest operations work on list as well as vectors! They also work on hash-maps as well. If you understand fundamental properties of data structures clojure guarantees that it matches expected performance characteristics. This is amazing when we consider the fact that all clojure data structures are immutable i.e. once defined they are final and do not change. E.g. if we updating value in hash-map produces new hash-map instead of actually changing old one.

There are lot more functions to explore for these data structure. Go through documentation of [assoc](https://clojuredocs.org/clojure.core/assoc), [cons](https://clojuredocs.org/clojure.core/cons), [peek](https://clojuredocs.org/clojure.core/peek), [pop](https://clojuredocs.org/clojure.core/pop),
[conj](https://clojuredocs.org/clojure.core/conj)

In next article we will try do define things and use them!
