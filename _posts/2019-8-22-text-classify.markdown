---
layout: post
title:  "Text classification"
date:   2019-07-08 22:17:56 -0400
categories: nlp
---

This is a walkthrough of my attempts to run text classification at my work.

# Background
Recently, people have been trying to organize and classify cyber threat data. There's this thing called the **MAEC (Malware Attribute Enumeration and Characterization)** vocabulary, which is basically a way to talk about malware which computers can understand (think XML).

# The problem
There's a lot of papers on cyber data. We want to read through them faster, so we want to use computers to help understand them.

# The data
[SemEval 2018, Task 8][SecureNLP]. The authors annotate sentences from cybersecurity reports with tags of varying levels of complexity. The hardest ones are malware attributes from - you guessed it - MAEC!

[SecureNLP]: https://www.aclweb.org/anthology/S18-1113

# The goal
Build a model that classifies these attributes from the text.

