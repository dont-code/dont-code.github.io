---
title: For Developers
---

## how the project is organized ?
The framework is organized into multiple repositories in [Github](https://github.com/dont-code).

- [Core](https://github.com/dont-code/core):
  A pure typescript library, deployed in npm as [@dontcode/core](https://www.npmjs.com/package/@dontcode/core).
  It provides the common application schema and api to manage an extensible application design platform based on realtime messages.
  It only has a dependency to Rxjs, so it can be used with any UI framework.
- [Ide-ui](https://github.com/dont-code/ide-ui):
  An Angular application that reads the application schema, potentially extended by plugins, and provides a means for the user to describe their applications based on this schema.
  It displays a set of questions, and pushes change messages each time the user make an answer 
- [Preview-ui](https://github.com/dont-code/preview-ui):
  An Angular application listening to these change messages and showing results in realtime.
  It provides as well a debugger page for emulating changes and testing your plugin:
  ![Previewer Debug](/assets/Previewer%20with%20debug%20page.png)
- [Plugins](https://github.com/dont-code/plugins):
  Contains multiple plugins and a common library to support them. You can use this as an example on how to develop plugins for Dont-code
- [Ide-Services](https://github.com/dont-code/ide-services):
  The Ide-ui connects to this service to push change messages, and this service will store them. For now, it's sending them to the Preview-Service.
  Developed in Java / [Quarkus](https://www.quarkus.io)
- [Preview-Services](https://github.com/dont-code/preview-services):
  The Preview-ui connects to this service to receive the change messages.
  Developed in Java / [Quarkus](https://www.quarkus.io)
 

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