+++
date = "2017-07-09T10:01:39+05:30"
title = "GSoC Week 5: Caching in with selectize"
author = "Sebastin Santy"
draft = false
tags = ["GSoC","Mozilla", "BMO"]
categories = ["category"]
description = "GSoC Week 5"
+++

Hi everyone!

This post comes very late than scheduled. My phase evaluations got over last week and questions were only based on mentor evaluations. We did face some hurdles even after the model prototype was designed, which delayed the PR to over one week.

## Work

The primary problem was that the BFCache wasn’t functioning as expected. All forms in BMO have this feature inherently and hence there was no way, the PR was to be merged. BFCache stands for back-forward cache. The heavy jquery manipulations I performed on the `<select>` elements to AJAX-load data, was what was causing the problem with BFCache.

To overcome this, we chose to go with [selectize.js](https://selectize.github.io/selectize.js/) which helps in loading data with customizations along with the implementation of BFCache. Over discussions, we also thought of replacing the existing prodcompsearch module with the tagging feature of selectize. In short, there are a lot of features in selectize which can be exploited in future. One minor challenge was to match selectize’ design with the BMO guidelines, by hacking some CSS.

## Conclusion

The patch has been merged, and I am now looking forward to implement the other modules into new-bug. Due to less people in my team (with atoll going out), I also help in reviewing patches occasionally. I received my first stipend of 720$ after the evaluations and now excited to complete the remaining project in time.

Signing off. Until next time :)