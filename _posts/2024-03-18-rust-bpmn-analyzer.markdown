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
My [research paper](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/publications/BPMN_Analyzer_2.0.pdf) about the analyzer is published at the Demonstrations & Resources Forum co-located with the 22nd International Conference on Business Process Management (BPM 2024).
In the following YouTube video I demo the BPMN Analyzer 2.0:

<div style="text-align:center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/Nv2W-hXNZYA" title="BPMN Analyzer 2.0 Demonstration" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

The BPMN Analyzer 2.0 has three _ambitious_ goals:

1. **Instantaneous analysis** (< 500ms) of realistic BPMN models.
2. **Understandability** of the found control-flow errors (clearly showing their cause).
3. **Automatic quick-fixes** for the most common control-flow errors.

The analyzer can easily be integrated into BPMN modeling tools like [bpmn.io](https://bpmn.io/) as in our [demo](https://timkraeuter.com/bpmn-analyzer-js/) to provide instant feedback during modeling.
In the screenshot below, one can see control-flow errors highlighted in red and quick-fix suggestions in green.

[![Modeling with the BPMN Analyzer 2.0 enabled](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/rustBPMNAnalyzer/modeling.png)](https://timkraeuter.com/bpmn-analyzer-js/)

To understand control-flow errors, the analyzer can visualize the possible execution that led to the error.
The following screenshot shows how the analyzer visualizes the execution leading to a process getting stuck.

[![Error example in the BPMN Analyzer 2.0](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/rustBPMNAnalyzer/counter-example.png)](https://timkraeuter.com/bpmn-analyzer-js/)
