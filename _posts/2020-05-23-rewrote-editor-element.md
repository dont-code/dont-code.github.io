---
title: "Rewrote Editor Element Management"
excerpt_separator: "<!--more-->"
categories:
  - Dev Diary
tags:
  - Builder
  - Code
---

To support plugins in the editor, I need to be able to display different editor elements depending on a selection.
<!--more-->

For example, the [Screen Plugin](https://github.com/dont-code/plugins/lib/screen) adds a screen type item, that when selected to 'list' for example, will ask the user only about
the entity name to display in the list.

So the default elements of a screen, like 'components' should be removed as they are not necessary.
The handling of editor elements is done in [TextService](https://github.com/dont-code/ide-ui/blob/master/apps/ide-ui/src/app/shared/text/services/text.service.ts) class, with maps of lists and so on. Complexity is high !

Now I changed this and [EditorElement](https://github.com/dont-code/ide-ui/blob/master/apps/ide-ui/src/app/routes/editor/editor-element.ts) stores their children directly, this simplifies a lot the code, I just spent 2 days rewritting it.
Two days with no new functionalities added, but now the code is simpler and ready for dynamic editing.  
I even removed intermediary classes that were not needed anymore... Cool
