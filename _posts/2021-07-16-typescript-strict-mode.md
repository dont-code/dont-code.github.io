---
title: "Strict Typescript"
excerpt_separator: "<!--more-->"
categories:
  - Status
tags:
  - Development
  - Typescript
  - Angular

---

After the move to Angular 12, we have upgraded all the projects to follow the 'strict' rules from Typescript.
This means making subtle changes in almost all source code.
<!--more-->

With this ['strict' mode](https://angular.io/guide/strict-mode), the typescript compiler is now checking all assignments to ensure null and undefined values are managed properly.
For example,
`  let value:string = aMap.get('something');`
triggers an error 'Cannot assign string|undefined type to string variable'.

Because when you declare `let value:string` in strict mode you are explicitly telling the compiler that value cannot be null or undefined.

As `aMap.get('something')` can return undefined, the compiler catches this.
The compiler will do the same checks for function return values, parameters, class members, and so on!

You can solve this in 2 ways basically:

**1- Either explicitly allow null values in this variable:**

`  let value?:string = aMap.get('something');`

Be aware that may trigger other errors in the code, for example if you are calling a function with this variable as parameter: The function itself must specify it accepts undefined values !

**2- Or separate undefined value handling:**
```
  const value = aMap.get('something');  // value's inferred type is string or undefined
  if (value) {
      // compiler knows var cannot be undefined or null here
  } else {
      // Special treatment if no values are found
  }
```

The result of all this hopefully gives developers more hints at potential nasty bugs in their code, at the expanse of speed of development and code clarity. Let's see if in the Dont-code case this is worth the effort.
