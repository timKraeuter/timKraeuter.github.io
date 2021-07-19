---
title: ":beetle: Visual Debugging in IntelliJ"
layout: post
date: 2021-07-19 10:30
tag:
- debugging
- visualization
- IntelliJ  
  image: https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/visualDebugger/pluginIcon.svg
  headerImage: true
  projects: true
  hidden: true # don't count this post in blog pagination
  description: "This is an app to calculate your gymnastics difficulty for all the gymnasts out there."
  category: project
  author: timKraeuter
  externalLink: false
---

A software developer spends a large amount of their time validating and debugging
software.
Traditionally, debuggers depict information in a text-based format.
I implemented an open-source plugin for IntelliJ IDEA, which visualizes the program state as an object diagram during debugging.

![Screenshot](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/visualDebugger/overview.png)

---

For complex debugging scenarios, you can set the depth of visualization when using the visual debugger.
In addition, you can export the current visualization as an SVG file.

If you want a detailed explanation of the plugin checkout my paper [here](https://github.com/timKraeuter/Visual_Debugging_in_IntelliJ/blob/main/Visual_Debugging_in_IntelliJ.pdf).

---

Check the plugin out [here](https://plugins.jetbrains.com/plugin/16851-visual-debugger) if you are curious!
