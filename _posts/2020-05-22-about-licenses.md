---
title: "Licenses for dont-code"
excerpt_separator: "<!--more-->"
categories:
  - Community
tags:
  - Licenses
  - Plugins
  - Core
---

I'm not really an expert in licenses, so I'm not sure my current choices will be the right ones.

There are several parts to the dont-core framework, and as they serve different purposes, they have different licenses.
<!--more-->

1. The [core library](https://github.com/dont-code/core) framework is used by all components, and I want anyone interested to be able to use it.
So for it I selected the most permissive license I'm aware of: the **MIT license**.

2. The [Builder](https://github.com/dont-code/ide-ui) and [Previewer](https://github.com/dont-code/preview-ui) can be both rewritten as long as they follow the guidelines defined by core.
    
    However I don't want them to be used without something in return, so they are under **AGPL license**.

    That means you can derive your work from it, and even run them in your public cloud, but any changes to it must be open-sourced as well.

