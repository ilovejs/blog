+++
showonlyimage = true
draft = false
image = "/img/clojure/clojure_spec.png"
date = 2017-10-21T16:04:01+11:00
title = "Note taken from David Nolen's Talk on Clojure Spec"
weight = 0
tags = [ "Development", "Clojure", "Blogging" ]
categories = [ "Development" ]
series = [ "Clojure Dev" ]
slug = "clojure_spec"
+++

Watched a talk by David Nolen about clojure.spec

URL: https://www.youtube.com/watch?v=Rlu-X5AqWXw


New features give you ability to:

* run quick check kind of test, find the minimal failing case.
* define function spec
* recursively parse the data using spec, so it works on tree
* write spec to check existing function
* find the problem of open source project, get rid of positional argument, because they are error-proned.
* generate examples from your spec, using `exercise`
* merge spec by `s/cat`
* describe a spec `describe`


Write code that meet expectations !!

