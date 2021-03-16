---
title: For Developers
---

## how is it working ?
**It provides an Application builder**
![Image](/assets/Application%20Builder.png)
with pre-defined questions.

Filling up the values let you express what you want to do with the application.


**It provides as well a Preview Application**
that shows you in realtime the result of your changes.
![Previewer](/assets/Preview.png)
As well a Debuger window allowing you to test your plugin:
![Previewer Debug](assets/Previewer%20with%20debug%20page.png)
## Plugin system
Dont-code only provides the core system, with extensive support for plugins.

With version 1.0 of the project, one could write a plugin for:
- [x] Adding new types of element to be edited and previewed
- [ ] Adding new fields type (address, short text, long text, pdf, who knows ?)
- [x] Enhancing existing entities with additional features
- [ ] Enabling queries inside the model (like, pre-filter selectionable items)
- [ ] Provide new Datastorage, extending the server-side storage capabilities


## How can I help?
If you believe in this project, there are several ways you could help.
Well all areas need help... 

- [ ] Obviously this website needs to be more engaging
- [ ] The core system is made of complex Typescript, some great technical challenges! Like the dynamically loading of plugins
- [ ] The build pipeline, done in Github Actions, needs to be streamlined
- [ ] For Angular developers, both the Editor and Previewer needs your attention
- [ ] The server-side part in Java / [Quarkus](https://quarkus.io) needs to be developed
- [ ] Custom plugins can be developed, see the list of possibilities above
- [ ] A Runtime (or code generator) needs to be written