---
title: "Support for currencies"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Field
  - Currency
  - Money
  - Euro

---

Now the basic types Currency have been added. You can now start designing finance apps.
<!--more-->

Thanks to the great [PrimeNG UI components](https://www.primefaces.org/primeng/), the Previewer now allows you to edit amount in your Currency.

![Entering Euro](/assets/enter-euro-amount.gif)

List of currencies has been added as well.

This took much more effort than for dates and images because I wanted to define a standard way of handling Money [with amount and currency](https://github.com/dont-code/core/blob/master/node/libs/core/src/lib/model/money-amount.ts), and I had to tweak the Dont-code framework itself to support multiple elements management by one field component.
