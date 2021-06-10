---
title: For Developers
---

## Dont-code Platform layers
To enable a user's friendly way to design an application, while supporting high level of customization by plugins, the platform consists of several layers:
The following diagram describe them:

![Dont-code Layers](/assets/dont-code-layers.png)

From a bottom-up perspective, one can see
- The Dont-code Platform itself provides functionalities for loading plugins, extending application model, handling events on the model. The core is developed in Typescript and is independent of any libraries, except RxJs. It provides Java mapping as well for server-side development.
- A Plugin developed for Dont-code describes its behavior using the [Extension meta-model](https://github.com/dont-code/core/blob/master/node/libs/core/src/assets/schemas/v1/plugin-config-schema.json). This is read by the Dont-code platform upon loading the plugin, and the changes described in it are applied to the application model.
- Any application designed for the Dont-code is following this [Application meta-model](https://github.com/dont-code/core/blob/master/node/libs/core/src/assets/schemas/v1/dont-code-schema.json). This is basically a json schema that can be modified by plugins. This meta-model is the heart of Dont-code:
  - It is used by the Builder to dynamically create questions and get input from the users.
  - It is used by the Previewer to select the right user interface component to use.
  - It is used to generate events whenever a change the application design changes.
- Plugins provide the User Interface components. Using the Extension meta-model, they register themselves for example to edit or display a particular field type, or complete new screens or workflows, or connect to other systems, and so on... For now, as the Builder is developed in Angular, the components must be compatible, but nothing prevents you from using other frameworks.
- With all these layers at his disposal, the user can design its custom application. The Dont-code framework updates in realtime a json representation of it, compatible with the Application Meta-model enhanced by plugins. This json is saved / loaded as projects.
- When the Previewer loads an application, it checks the description of entities and fields, and it adapts the user interface. The user can then see and edit values that are stored. This becomes the application's data.

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
- [Project-Services](https://github.com/dont-code/project-services):
  Used to list, store and load projects
  Developed in Java / [Quarkus](https://www.quarkus.io)
 

## Plugin system
Dont-code only provides the core system, with extensive support for plugins.

With version 1.0 of the project, one could write a plugin for:
- [x] Adding new types of element to be edited and previewed
- [x] Adding new fields type (address, short text, long text, pdf, who knows ?)
- [x] Enhancing existing entities with additional features
- [ ] Enabling queries inside the model (like, pre-filter selectionable items)
- [x] Provide new Datastorage, extending the server-side storage capabilities


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