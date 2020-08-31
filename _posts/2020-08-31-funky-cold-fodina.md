---
layout: post
title: Funky Cold Fodina Dependencies
tags: process-mining Fodina dependencies
---

[Fodina](http://www.processmining.be/fodina/) is an advanced process discovery algorithm based on the Heuristic Miner lineage. I had a bit of trouble installing it based on the installation instructions, though. There were some `NoClassDefFoundErrors` complaining about jgoodies classes not bundled in the `fodina-libs-2019-06-17.jar` file provided.

The two missing jgoodies jars are:
 + `jgoodies-common-1.3.1.jar`
 + `jgoodies-forms-1.5.1.jar`

They are available from the same site under the [download area](http://www.processmining.be/fodina/downloads/), they're just missing from the instructions.



