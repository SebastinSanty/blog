+++
date = "2017-06-21T17:53:07+05:30"
title = "GSoC Week 3: REST the bugs"
author = "Sebastin Santy"
draft = false
tags = ["GSoC","Mozilla", "BMO"]
categories = ["category"]
description = ""

+++

Hi, so this week was a time in which a good portion of work amounted to my actual coding and creativity. Till last week, it was about getting elements from bug_modal design and placing them accordingly.

## Work

[Bug 1365344](https://bugzilla.mozilla.org/show_bug.cgi?id=1365344): The work here was to include the Status and Null Modules in the new_bug interface. The null module includes Summary and the Status module includes Product, Component and its description. One of the features which is pending and needed to be added at the end is the BMO’s prodcompsearch feature. Also this feature saw the removal of specific codes (bugzilla_ajax) from `common_bug_modal.js` file to a new one, made particularly for new_bug.

[Bug 1373000](https://bugzilla.mozilla.org/show_bug.cgi?id=1373000): This came as a blocker to the above bug. It was about making of the REST APIs to accomplish the tasks of retrieving products and components async. Earlier this was implemented in the bug_modal API, the downside of which was, to have a bug number passed for the same. This means it was bug specific and a general API had to be designed.


## Conclusion:

From last two weeks, I got sure that not everything comes from the textbook. During making of my gsoc proposal, I and my mentor considered various aspects of the new_bug.cgi except the transfer of bug_modal design. It turns out that, bug_modal is the biggest headache to the project as it has been tightly knit to the existing `show_bug.cgi`.
