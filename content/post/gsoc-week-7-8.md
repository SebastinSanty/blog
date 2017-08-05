+++
date = "2017-07-26T23:56:06+05:30"
title = "GSoC Week 7 & 8: Style it like Github"
author = "Sebastin Santy"
draft = false
tags = ["GSoC","Mozilla", "BMO"]
categories = ["category"]
description = "GSoC Week 7 & 8"
+++

Hi everyone,

So these weeks some radical changes happened in terms of design. The new-bug design was looking uglier day-by-day, as we were shamelessly copying the bug modal design which is actually suited for show_bug.cgi. So it was planned we’ll go with re-organizing parts of the layout and also implementing keywords feature.

## Work
After lots of discussion with my mentor, we decided to approach Kohei Yoshino (mozilla.org designer and UX expert) and his inputs were really valuable. He suggested us to go with the github issues styling and that was one good of a decision. Implementing keywords feature was easy, as selectize had a built in support for multiple tagging.

## Conclusion
Here is how it looks now:
![Github Like New-Bug Image](/static/github_like.png)

At present, I am working on clearing attachments PR and also a new feature by which users will be able to give product names in the URL using hash, like this -  
`https://bugzilla.mozilla.org/new-bug#Core`. This will be useful for power users of BMO.