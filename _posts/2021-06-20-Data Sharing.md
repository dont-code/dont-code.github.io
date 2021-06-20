---
title: "Sharing data"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Data
  - Server
  - MongoDB

---

Now you can share information with other users
<!--more-->

Available today, you can select "Share with Dont-code users" in the [Builder](https://dont-code.net/ide-ui/).

You know you can directly edit data in the [Previewer](https://dont-code.net/ide-ui/) while designing your application. Until now, this data was saved in your local computer (in the [Browser's IndexedDB](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)).
However, if you select 

![Share data](/assets/share-data.gif)

, then the data will be stored through the [Dont-code Data API](https://github.com/dont-code/data-services) provided by our Test server and stored in a MongoDB Database.

This means another user selecting the same project will be able to see and edit the same data. Another step in the journey of a usable no-code platform.