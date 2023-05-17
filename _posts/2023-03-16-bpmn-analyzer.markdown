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
hidden: true # don't count this post in blog pagination
description: "This is a tool to analyze BPMN process models to find bugs during design time before the implementation starts."
category: project
author: timKraeuter
externalLink: false
---

The Business Process Modeling Notation (BPMN) is a widely used standard notation for defining intra- and inter-organizational workflows.
It is heavily for process automation and orchestration in [many businesses](https://camunda.com/about/customers/).
Formalizing BPMN reduces the cost of business process automation by facilitating the detection of errors and optimization potentials in process models already during design time before the implementation starts.
The [BPMN Analyzer](https://bpmnanalyzer.whitefield-c9fed487.northeurope.azurecontainerapps.io/) is an [open-source](https://github.com/timKraeuter/Rewrite_Rule_Generation) tool to analyze BPMN process models formally.

The tool supports [most BPMN constructs](https://github.com/timKraeuter/Rewrite_Rule_Generation/wiki#feature-support-comparison) used in practice and allows checking behavioral properties.
Especially, it can check if a BPMN model contains dead activities (activities which can never be executed) or cannot terminate.

I published a research paper about the formalization used in the tool at the 16th International Conference on Graph Transformation (ICGT 2023).
For more information look at the corresponding [preprint](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/publications/Formalization_and_analysis_of_BPMN_using_graph_transformation_systems.pdf).
