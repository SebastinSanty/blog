+++
date = "2017-06-25T23:27:08+05:30"
title = "GSoC Week 4: Here comes the protoype"
author = "Sebastin Santy"
draft = false
tags = ["GSoC","Mozilla", "BMO"]
categories = ["category"]
description = ""

+++

Hi everyone! Next week is the Phase I evaluations for my GSoC project. I have been able to finish the prototype as planned in my proposal.

## Work

[Bug 1365345](https://bugzilla.mozilla.org/show_bug.cgi?id=1365345): The work involved winding up the previous month’s work of unusable bits into a working prototype. There were two issues faced during this:

1) **Tracking Module**: `Bugzilla::Bug` object required a mandatory version field, which was lacking on the interface. Before the work on prototype started, we only had the `Status` and `Null` Modules. But because of the inclusion of version, `Tracking` module also needed to be introduced. This also meant, the previous AJAX call designed for the components had to be extended to retrieve the versions too.

2) **Extending API**: As discussed above, the components API was extended to facilitate the retrieval of `versions`. Also, as a result of this, the `components` API was renamed to `product_info`, to indicate its use properly.

## Conclusion

As the Phase I of GSoC is getting over, the major hurdles of setting up the inferface is done with and a flow has been created. Now it would be easy to extend the functionality of the new-bug interface. Here’s a look of how the new-bug interface looks like, till now:

![Prototype Image](/static/phase1prototype.png)

