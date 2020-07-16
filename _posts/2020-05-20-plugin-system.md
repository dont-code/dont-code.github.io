---
title: "Working on plugin system"
excerpt_separator: "<!--more-->"
categories:
  - Plugins
tags:
  - Development
  - Plugins
---

## One of the most important part is the plugin system.

To be successful and different from other low-code or no-code frameworks, dont-code should be as extensible as possible. 
<!--more-->

This way, persons or companies from all over the world will be able to use and add any kind of functionalities.

Of course, this is quite complex as you must allow changes in the core of the framework from external.

## This is why I need to:
- [x] Create a [core library](https://github.com/dont-code/core), linking together the [Builder](https://github.com/dont-code/ide-ui), the [Previewer](https://github.com/dont-code/preview-ui) and the [Plugins](https://github.com/dont-code/plugins)
- [x] Enable plugins to register to core
- [x] Re-write partially the Builder to support dynamic schema as it is being updated by plugins
- [x] Tidy up the editor to enable options overloading and reordering
- [x] Enable the plugin to register with the Previewer
 
## It is starting to work now

For example, a plugin can add a list of options named 'type' to the editor by registering with
```json
     {
    "schema-updates": [{
        "id": "screen-list",
        "description": "A screen displaying a list of items",
        "changes": [{
          "location": {
            "parent": "#/definitions/screen",
            "id": "type",
            "after": "name"
          },
          "add": {
            "enum": [
              "list"
            ]
          },
          "props": {
            "entity": {
              "$ref": "#/definitions/entity",
              "format": "#/creation/entities"
            }
          },
          "replace": true
        }]
      }]
    }
``` 
## The result is this:

![Builder showing type list from a plugin](/assets/builder-with-type-from-plugin.png)

Of course, it is placed only at the end for now, it should as well replace the other options of screens, but it's a start.
