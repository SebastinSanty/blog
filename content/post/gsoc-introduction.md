+++
date = "2017-05-30T11:49:35+05:30"
title = "GSoC 2017 with Mozilla"
author = "Sebastin Santy"
draft = false
tags = ["GSoC","Mozilla", "BMO"]
categories = ["category"]
description = ""

+++

Hello everyone!

So as I mentioned in my previous post, here is what I'll be working on, this Summer. Having worked with Mozilla for around 10 months on multiple projects, now for Google Summer of Code (GSoC), I will be working on the project **"Improving bug filing interface for [bugzilla.mozilla.org](https://bugzilla.mozilla.org)"** with the [Mozilla B-Team](https://wiki.mozilla.org/BMO#B-Team).
### Inception

I started off with Firefox, submitted around 10 patches and was an active contributor during June and July. That is when I stumbled on the Bugzilla Project, not surprisingly through a bug. That is the start of my long association with the Mozilla B-Team. [Dylan Hardison [:dylan]](https://www.linkedin.com/in/dylanwh/) has been constantly helping and mentoring me, all through these months. The fact that there are less people in the B-Team helped me in constant involvement with the team.

In late January, I simultaneously started contributing to [Treeherder](https://treeherder.mozilla.org), owing to my knowledge in Django and Angular. [William Lachance [:wlach]](https://www.linkedin.com/in/wrlach) was kind enough to give me an interesting project "Replacing REST APIs with GraphQL" which I am still working on, alongwith [Cameron Dawson [:camd]](https://www.linkedin.com/in/cameron-dawson-a9a41a/) as William moved on to the telemetry project (I have a lot more to say about this, but in a later post).

Finally, after discussing with my mentors, I decided to pick the project to improve bug filing interface for bugzilla.mozilla.org.

### My Project

My work is with the Mozilla's version of Bugzilla Project, called bugzilla.mozilla.org (BMO). At present BMO uses enter_bug.cgi to file bugs. People filing bugs on BMO frequently, are aware of how tedious the process of filing bugs is. Some of the existing problems I intend to solve are:

1. Presence of multiple views for different types of users: simple, advanced, and the "guided" wizard-like system, is an issue. The new interface will have a single-page interface.

2. Presence of a lot of legacy code, taken from the upstream (Bugzilla Project), which makes it difficult for even developers to make any substantial changes, or create custom form wrappers over them. This calls for a green-field approach. So instead of working on enter_bug.cgi, I'll be creating a new cgi script (new_bug.cgi), which will work in parallel to the former, until it is cleared of all the bugs.

3. The most biggest problem is that bug filing consumes a lot of time. There are two parts to this issue:

    1. enter_bug.cgi is completely dependent on Template Toolkit rendering of html pages. The parts of the templates that are slow involve loops over huge lists of things. Core developers of Firefox routinely leave open tabs because loading bug filing page for the Core product takes upwards of 8 seconds. The new interface will have less dependence on backend rendering, and will rely more on AJAX loading of data.

    2. Also submitting the bugs takes a good amount of time. This is because, enter_bug.cgi is a stateless CGI that posts form data to post_bug.cgi which subsequently makes a database entry. This is easily confused with process_bug.cgi, which is the backend for show_bug.cgi. Having a unified place in the web UI for bug creation would be a cleaner design. 

Other than solving the above problems, I will also take into consideration new features like Bug Modal design (which was used for the current show_bug.cgi) while building this project. The meta-tracking bug for the project is [Bug 1365317](https://bugzilla.mozilla.org/show_bug.cgi?id=1365317)

Thanks for going through my long post. I hope to complete the GSoC Project with *Zarro Boogs* (you should know the Bugzilla slang to understand this! :) ). Signing off. Until next time :-).