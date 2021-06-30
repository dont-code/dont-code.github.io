---
title: "Added new field types"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Field
  - Date
  - Image
  - Url

---

Less than 2 days needed to add support for date, time, image and url.
<!--more-->

Thanks to the plugin architecture it took me just a few hours to add new field types to the Dont-code platform...
I just needed to copy / paste the code for the basic fields (Text, Long, Numeric) and update the Angular templates to use [PrimeNg Calendar Component](https://primefaces.org/primeng/showcase/#/calendar).

In fact, most of the time was spent adding support for grouping field types due to the increasing number of them:

![Menu](/assets/Builder%20grouped%20field%20types.png)

Next step is to add Currencies and Monetary Amount field types. Let's see how much effort will be needed for that !
