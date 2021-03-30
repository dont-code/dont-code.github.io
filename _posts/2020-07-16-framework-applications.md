---
title: "Dontcode Framework Applications"
excerpt_separator: "<!--more-->"
categories:
  - Architecture
tags:
  - Builder
  - Previewer
  - Components
---

Two applications work together to enable the development of applications without coding.
Let's describe them...
<!--more-->

1. The [Builder](https://github.com/dont-code/ide-ui) is the Development Environment. It shows you pre-defined sentences, and you simply have to fill the blanks.
It is running in Angular + Angular Material
![Screenshot](/assets/Application%20Builder.png)

2. The [Previewer](https://github.com/dont-code/preview-ui) is where you see the result in realtime. It is connected to the Builder and reacts automatically to editions you make in the Builder
It is running in Angular + [PrimeNG UI](https://www.primefaces.org/primeng/)

For example, 
- Start the [Builder demo](https://dont-code.net/ide-ui/), then have it open the Previewer
![by clicking here](/assets/Builder%20open%20Previewer.png)
- The previewer opens with default screen 
![Previewer default](/assets/Previewer%20just%20opened.png)
- Then back to the editor, and change the application name
![Change app name](/assets/Builder%20change%20app%20name.png)
- See immediatly the builder just updated its title:
![Previewer name change](/assets/Previewer%20with%20name%20test.png)
- Same if you add a new screen in the editor
![Builder new screen](/assets/Builder%20with%20new%20screen.png)
- It creates a menu in the Previewer:
![Previewer with menu](/assets/Previewer%20with%20menu%20editor.png)

