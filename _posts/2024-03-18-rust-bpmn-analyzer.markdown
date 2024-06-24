---
title: "BPMN Analyzer 2.0: Instantaneous BPMN control-flow analysis and error resolution :fire:"
layout: post
date: 2024-03-18 18:00
tag:
- BPMN
- control-flow analysis
- quick fix
image: https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/bpmnAnalyzer/icon.svg
headerImage: true
projects: true
hidden: false # don't count this post in blog pagination
description: "This is a tool to analyze BPMN process models to find, display, and fix control-flow errors already during modeling."
category: project
author: timKraeuter
externalLink: false
---
The **BPMN Analyzer 2.0** is a tool to analyze BPMN process models to find, display, and fix control-flow errors already during modeling.
Unlike my previous [BPMN Analyzer](https://timkraeuter.com/bpmn-analyzer/), this tool is written in Rust and uses a pragmatic encoding of BPMN semantics for optimal performance regarding control-flow analysis.
A demo version of the analyzer is hosted [online](https://timkraeuter.com/bpmn-analyzer-js/) and the source code is open-source ([front-end](https://github.com/timKraeuter/bpmn-analyzer-js), [back-end](https://github.com/timKraeuter/rust_bpmn_analyzer)).
The following is a screenshot of our demo version:

<!-- 
I could make a YouTube demonstration and add it here. For now, I will add a screenshot.
-->
![Modeling with the Rust BPMN Analyzer enabled](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/rustBPMNAnalyzer/modeling.png)

The BPMN Analyzer 2.0 has three _ambitious_ goals:

1. **Instantaneous analysis** (< 500ms) of realistic BPMN models.
2. **Understandability** of the found control-flow errors (clearly showing their cause).
3. **Automatic quick-fixes** for the most common control-flow errors.

The analyzer can easily be integrated into BPMN modeling tools like [bpmn.io](https://bpmn.io/) as in our [demo](https://timkraeuter.com/bpmn-analyzer-js/) to provide instant feedback during modeling.
In the screenshot above, one can see control-flow errors highlighted in red and quick-fix suggestions in green.

To understand control-flow errors, the analyzer can visualize the possible execution that led to the error.
The following screenshot shows how the analyzer visualizes the execution leading to a process getting stuck.

![Error example in the BPMN Analyzer 2.0](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/rustBPMNAnalyzer/counter-example.png)
