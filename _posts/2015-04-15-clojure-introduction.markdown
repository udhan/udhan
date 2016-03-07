---
layout: post
title:  "Clojure Introduction"
date:   2015-04-15 01:40:56 -0800
categories: en
tags: clojure lisp programming
---

Clojure is a lisp dialect which mainly targets JVM. I wanted to learn lisp since my close encounter with it as emacs-lisp. Its simple syntax and the fact that we write AST itself changed my perspective about programming languages. However I am expecting steep learning curve as lisp is totally different than any other language that I know. Thinking in prefix notation is not going to be easy.

So lets begin!

### Installation
I am not going to repeat how to install clojure here.
Go to http://clojure.org/getting_started and follow the instructions. At the end you will have repl up and running. Awesome!

### Basic syntax

    hello.core> (+ 3 4)
	7
	hello.core> (+ 1 2 3 4 5)
	15
	hello.core> (+ 1, 2, 3, 4, 5)
	15
    hello.core> (str/blank? "")
	true
	hello.core> (str/blank? "")
	true
	hello.core> (str/blank? "88")
    
Lets try to learn what examples demonstrate about clojure syntax.

- Prefix notation: `e.g. (+ 3 4)`
- First element in list can be a function name or operator. In fact there is no difference between function and operator. plus (+) operator here is just another function name.
- You can have namespaces `e.g. str or hello`
- Commas are ignored in lists
- Strings are surrounded by double quotes
- REPL is awesome! :)
