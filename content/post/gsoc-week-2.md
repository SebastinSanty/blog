+++
date = "2017-06-12T18:50:19+05:30"
title = "GSoC Week 2: Some bugs here and some vagrant there"
author = "Sebastin Santy"
draft = false
tags = ["GSoC","Mozilla", "BMO"]
categories = ["category"]
description = ""

+++

As the second week of GSoC comes to an end, I have been able to cover three major bugs till now.

## Work

[Bug 1365340](https://bugzilla.mozilla.org/show_bug.cgi?id=1365340): A new bug interface has been created. This loads up on `/new-bug` which is served by the new_bug.cgi script. This went pretty much easy, as this only needed loading of a page. The result is live in action: [https://bugzilla.mozilla.org/new-bug](https://bugzilla.mozilla.org/new-bug)

[Bug 1365342](https://bugzilla.mozilla.org/show_bug.cgi?id=1365342): The first major task was to move `new_comment` functionality to `new-bug`. This was one of the challenging tasks, as several components used in the new bug modal design were tightly coupled with the `show_bug.cgi` for which the design was originally deployed. A workaround which we came up was to make copies of the same components with a `common-*` prefix and then reduce and shift around functionalities, so that it becomes generalized by the end of GSoC period. This means that the end result of GSoC will also consist of generalization of Bug Modal Design to be used by other templates in addition to the new-bug interface

[PR 92](https://github.com/mozilla-bteam/bmo/pull/92): Another issue that propped in between was the ease of rapid debugging. Rapid debugging is especially required, when the work involves a lot of client-side work, as was my case in some of the initial tasks. The already available provisioner script was tedious, as this was only required to setup BMO locally. A new update provisioner script was designed to limit the time of execution from upwards of quarter of a minute to 6 seconds.

## Conclusion

I enjoyed working on some of the initializing bugs this week. And Oh, over a casual chat with my mentor, I came to know about something great: Bugzilla was (and is) used by NASA for its missions. Don't believe me, Check this out: 

![Example image](/static/bugzilla_nasa.png)

Signing off. Until next time :)
