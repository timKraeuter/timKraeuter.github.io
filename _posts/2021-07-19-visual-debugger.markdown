---
title: ":beetle: Visual Debugging in IntelliJ"
layout: post
date: 2021-08-23 10:00
tag:
- debugging
- visualization
- IntelliJ
image: https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/visualDebugger/pluginIcon.png
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
I implemented an [open-source](https://github.com/timKraeuter/VisualDebugger) plugin for IntelliJ IDEA, which visualizes the program state as an object diagram during debugging.
In many scenarios, graphical representations such as object diagrams are more understandable than textual representations when representing the state of an object-oriented system.
You can see the different representations in the following screenshot, which includes an object diagram view for the debugging variables on the right.

![Screenshot](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/visualDebugger/overview.png)

However, the view above is only a picture that does not allow any user interaction, while you can double-click on variables on the left to load more information about that variable.
Consequently, I have developed a browser-based visualization that allows user interaction. One can switch between the two implemented visualizations in the plugin settings.

![Screenshot](https://raw.githubusercontent.com/timKraeuter/timKraeuter.github.io/master/assets/images/visualDebugger/webUI.png)

The browser will connect via WebSocket to the plugin, such that it will receive live updates when the debugger variables changed due to IDEA input.
The UI is not tied to IntelliJ IDEA and can be used as a debugging view for other IDE's when debugging object-oriented code.

---

For complex debugging scenarios, you can set the initial depth of visualization when using the visual debugger.
In addition, you can export the current visualization as an SVG file.

<div style="text-align:center">
    <iframe frameborder="none" width="384px" height="319px" src="https://plugins.jetbrains.com/embeddable/card/16851"></iframe>
</div>

Check the plugin out [here](https://plugins.jetbrains.com/plugin/16851-visual-debugger) if you are curious!

---

If you want a detailed explanation of the plugin checkout my paper [here](https://github.com/timKraeuter/Visual_Debugging_in_IntelliJ/blob/main/Visual_Debugging_in_IntelliJ.pdf).

<div class="breaker"></div>

<div style="text-align:center">
    <iframe frameborder="none" width="245px" height="48px" src="https://plugins.jetbrains.com/embeddable/install/16851"></iframe>
</div>
