+++
date = "2017-07-13T01:04:24+05:30"
title = "Integrate GraphQL in Treeherder"
author = "Sebastin Santy"
draft = false
tags = ["Mozilla", "Treeherder"]
categories = ["category"]
description = "Integrate GraphQL in Treeherder"

+++

It was almost six months ago when over the general chat, [William](https://mozillians.org/en-US/u/wlach/) discussed the idea of integrating [GraphQL](http://graphql.org) with [treeherder](https://treeherder.mozilla.org). GraphQL is a novel standard created by Facebook, to replace existing clunky REST APIs.

## Why GraphQL

At its core when compared to REST, it stands out in two aspects mainly:  

1) REST APIs give out a lot of information than what might be required by the web interface. To put it short, REST APIs have a static structure, and for even getting one string, the whole JSON has to be retrieved. Large JSON, means more data needs to be both fetched from the database, serialized into a JSON response and transferred to the client.  

2) To retrieve several linked entities (relational), multiple requests have to be made when using REST APIs. GraphQL can get you data in one go.  

A possible solution to this does exist: Hand-coding of custom endpoints, but this is very tedious and may result in redundancy.  

As the above points suggest, GraphQL is highly dynamic. A user needs to query only the data it requires, in the form of a json “graph”, traversing across object types, and the API returns exactly what the user asked for, in a single response. This makes it easier to be used across various platforms, like data-sensitive mobile devices. The below picture accurately describes the difference.  

![REST vs GraphQL Image](/static/restvsgraphql.png)

There shouldn’t be any apprehensions when going production-level: Facebook has been using GraphQL since 2012. They open sourced the concept only in 2015.

## How does it help Treeherder

As noted by William on the bug[2]:

1) The jobs API endpoints provides a lot of data, much of which is unused by the frontend. For example, we hit this endpoint to get the jobs for display:

https://treeherder.mozilla.org/api/project/mozilla-inbound/jobs/?count=2000&result_set_id=226266&return_type=list

2) At the same time, getting different types of information pertaining to a job (performance data, job details, error summary lines) require multiple requests, which slows response time (every time you load the details panel for a job, 4+ http requests need to be processed).

There are also some new views coming up in treeherder (e.g. a manifest-based view) and these views will almost certainly need data that isn't in the main jobs table.

At present [Cameron](https://mozillians.org/dsb/u/camd/) is working enthusiastically towards this. I’ve started again after almost a month or two.

I hope, next post will have some good showcase of the implementation! Thank You :-)

References:  
[1] https://dev-blog.apollodata.com/why-graphql-is-the-future-3bec28193807  
[2] https://bugzilla.mozilla.org/show_bug.cgi?id=1332457  