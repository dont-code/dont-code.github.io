---
title: "Save & Load projects"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Project
  - Builder

---

Now one can save and load an application in the Builder.
<!--more-->

If you have a look at the [Application Builder Demo](https://dont-code.net/ide-ui), you'll see a new menu appeared: Projects.

Clicking on it, you'll see the project screen where you can save the current project or load another one.
![Project Save](/assets/builder-save-project.gif)

One can believe this would be an easy thing to develop, however even the development team were surprised to see how difficult it was.
Not only we had to:
 - Develop a new service to provide load/save project
 - Switch to a better server to support a database for the Demo application
 - Develop the screen in the builder to support load and save project workflow

However, we didn't expect the following issues:
 - As the Builder editor screen is built automatically based on a meta-model document, it needs to be rebuilt whenever a project is loaded.
 - The Builder shows the loaded project elements mixed with elements from the meta-model ready to be answered.
 - The meta-model itself is dynamic (updatable by plugins)

So all this brought complexity to the development of this feature. And fear is growing as it needs to be applied to the [Previewer](https://dont-code.net/preview-ui) as well. 
