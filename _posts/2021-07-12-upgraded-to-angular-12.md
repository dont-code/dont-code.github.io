---
title: "Upgraded to Angular 12"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Development
  - Angular
  - Nx.dev
  - PrimeNG

---

This week-end has been spent upgrading Angular to version 12, and that was an easy one.
<!--more-->

Of course this involves some mandatory steps:
- [Upgrade nx.dev workplace](https://nx.dev/latest/angular/core-concepts/updating-nx)
- [Update dependencies in package.json](https://github.com/dont-code/plugins/commit/5ceff360704eb1d181cea7edebb2ce775759467a#diff-7ae45ad102eab3b6d7e7896acd08c427a9b25b346470d7bc6507b6481575d519)
- [Update PrimeNg to version 12](https://www.primefaces.org/primeng-v12-0-0-is-here/)
- Run unit and e2e tests
  - Turns out I cannot use rxjs 7.x yet, as several libraries (include Angular 12) mandates rxjs 6.x
  - Some test scripts had to be amended - mostly due to problems not detected by previous versions 
  - A bad typescript code in my cypress additional functions to find angular components made tests hang
- Re-release dont-code/core, then dont-code/plugins, then dont-code/ide-ui and finally dont-code/preview-ui
- Re-deploy and test: Everything was working fine.

So it took me only a week-end to do this major upgrade, thanks [Angular](https://angular.io), [Nrwl](https://nex.dev), [Primetek](https://primefaces.org/primeng), [Jest](https://jestjs.io) and [Cypress](https://cypress.io), I know this went smooth thanks to your hard work!