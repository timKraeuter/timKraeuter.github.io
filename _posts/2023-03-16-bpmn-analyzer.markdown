---
title: "BPMN Analyzer: Formal analysis of BPMN process models :chart_with_upwards_trend:"
layout: post
date: 2023-03-16 10:45
tag:
- BPMN
- formalization
- model checking
image: https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/bpmnAnalyzer/icon.svg
headerImage: true
projects: true
hidden: false # don't count this post in blog pagination
description: "This is a tool to analyze BPMN process models to find bugs during design time before the implementation starts."
category: project
author: timKraeuter
externalLink: false
---

The Business Process Modeling Notation (BPMN) is a widely used standard notation for defining intra- and inter-organizational workflows.
It is used heavily for process automation and orchestration in [many businesses](https://camunda.com/about/customers/).
Formalizing BPMN reduces the cost of business process automation by facilitating the detection of errors and optimization potentials in process models already during design time before the implementation starts.
The [BPMN Analyzer](https://bpmnanalyzer.whitefield-c9fed487.northeurope.azurecontainerapps.io/) is an [open-source](https://github.com/timKraeuter/Rewrite_Rule_Generation) tool to analyze BPMN process models formally.

<div style="text-align:center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/MxXbNUl6IjE" title="BPMN Analyzer Tool Demonstration" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

The tool supports [most BPMN constructs](https://github.com/timKraeuter/Rewrite_Rule_Generation/wiki#feature-support-comparison) used in practice and allows checking behavioral properties.
Especially, it can check if a BPMN model contains dead activities (activities which can never execute) or cannot terminate.
The following screenshot shows the detection of a dead activity in a BPMN model. The activity can never execute due to wrong gateway usage.

![Screenshot of the BPMN Analyzer tool detecting a dead activity](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/bpmnAnalyzer/screenshot.png)

I published a [research paper](https://doi.org/10.1007/978-3-031-36709-0_11) about the formalization used in the tool at the **16th International Conference on Graph Transformation (ICGT 2023)**.
The paper won the **[&#9733; Best Paper Award &#9733;](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/BestPaperICGT2023.pdf)**.
You can read the [preprint](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/publications/Formalization_and_analysis_of_BPMN_using_graph_transformation_systems.pdf) of the paper for free.
