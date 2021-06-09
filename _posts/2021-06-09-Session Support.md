---
title: "Development Session"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Builder
  - Previewer
  - Session
  - Services

---

... has been implemented
<!--more-->

When you update your application model in the Builder, it shares all with the Previewer through a server.
This allows you to have the Previewer neatly separated from the Builder, and even starts multiple Previewers, all updated at the same time.
Now when you use the [Builder Demo](https://dont-code.net/ide-ui/), you can see at the top right a small popup:

![Popup Session](/assets/popup-session.gif)

You see the server it is connected to, and as well the Session used. Any modifications you're doing to your application design, is sent to the server and stored with this Session.
Then, when you Open the Previewer

![Open Previewer](/assets/open-previewer.gif)

it will display the latest updates of your application related to this Session.

In order to do that, I've used a [MongoDB database](https://mongodb.org) running on server side and storing all sessions updates.
The side effect is now I can see if and when people are using the demo.


