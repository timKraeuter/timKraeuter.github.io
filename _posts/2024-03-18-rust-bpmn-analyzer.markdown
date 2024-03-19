---
title: "Rust BPMN Analyzer: Instantaneous BPMN control-flow analysis and error resolution :fire:"
layout: post
date: 2024-03-18 18:00
tag:
- BPMN
- control-flow analysis
- quick fix
image: https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/bpmnAnalyzer/icon.svg
headerImage: true
projects: true
hidden: true # don't count this post in blog pagination
description: "This is a tool to analyze BPMN process models to find, display, and fix control-flow errors already during modeling."
category: project
author: timKraeuter
externalLink: false
---
The Rust BPMN Analyzer is a tool to analyze BPMN process models to find, display, and fix control-flow errors already during modeling.
Unlike my previous [BPMN Analyzer](https://timkraeuter.com/bpmn-analyzer/), this tool is written in Rust and uses a pragmatic encoding of BPMN semantics for optimal performance regarding control-flow analysis.
A demo version of the Analyzer is hosted [online](https://bpm-2024.whitefield-c9fed487.northeurope.azurecontainerapps.io/) and the source code will be open-source ([front-end](https://github.com/timKraeuter/bpmn-analyzer-js), [back-end](https://github.com/timKraeuter/RustBPMNAnalyzer)), after the review of my research paper about the analyzer.
The following is a screenshot of our demo version:

<!-- 
I could make a YouTube demonstration and add it here. For now, I will add a screenshot
-->
![Modeling with the Rust BPMN Analyzer enabled](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/rustBPMNAnalyzer/modeling.png)

The Analyzer has three _ambitious_ goals:

1. **Instantaneous analysis** (< 500ms) of realistic BPMN models.
2. **Understandability** of the found control-flow errors clearly showing their cause.
3. **Automatic quick-fixes** for the most common control-flow errors.

The Analyzer is integrated into BPMN modeling tools like [bpmn.io](https://bpmn.io/) in our [demo](https://bpm-2024.whitefield-c9fed487.northeurope.azurecontainerapps.io/) to provide instant feedback during modeling.
In the screenshot above, one can see control-flow errors highlighted in red and quick-fix suggestions in green.

To understand control-flow errors, the analyzer can visualize the possible execution that led to the error.
The following screenshot shows an example where the analyzer shows that two tokens can be located at the last sequence flow due to a lack of synchronization.

![Error example in the Rust BPMN Analyzer](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/rustBPMNAnalyzer/counter-example.png)
