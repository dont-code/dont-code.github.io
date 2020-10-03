---
title: "Plugin system working"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Plugin
---

A quick update as the plugin framework is now working
<!--more-->

We achieved quite a big step last week as the dont-code framework now supports loading plugins dynamically.
It supports two types of plugins:

- The plugins can modify the behavior of the [Builder](https://github.com/dont-code/ide-ui). It can modify the model used by dont-code to describe an application, then the builder automatically adapts the questions to support it.
For example, the [test screen plugin](https://github.com/dont-code/plugins/libs/screen) adds the type field to the screen, and changes editor fields dynamically when selected.
See the ![Video](/assets/Dynamic Editor Screen Type.gif).

- As well plugins can enhance the [Previewer](https://github.com/dont-code/preview-ui) by registering to display any items in the model.
The Previewer will call dynamically the registered plugin and push any information to it.

Of course you can combine both in a single plugin, allowing you to add or modify any item in the editor and handle its display in the previewer !

To further enhance the plugin framework and make sure it is performant enough, even the core ui components of the previewer will be developed as plugins. You can find the basic ones in the following [repository](https://github.com/dont-code/plugins/libs/basic)


