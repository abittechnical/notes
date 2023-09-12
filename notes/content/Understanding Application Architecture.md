---
tags: [Notebooks/Web Applications]
title: Understanding Application Architecture
created: '2019-12-25T03:32:47.297Z'
modified: '2019-12-26T05:21:50.551Z'
---

# Understanding Application Architecture

> Any good architecture is based on the fundamental engineering principle of **separation of concerns,** which helps in managing complexity by breaking a system down into smaller, functionally defined parts such that their **interdependencies are minimized,** keeping the more fundamental parts independent of the less fundamental parts. - Gerd Wagner

## MVC

Although it has not been precisely defined, and has been implemented in many different  ways, especially in web application frameworks, [MVC] is based on the principle of separation of concerns and on the fundamental insight that __the basis for all other  parts of an application, and in particular for the user interface, is the model__.

> MVC is explained as a *"three-way division of an application"*
That entails separating the parts that:
1. *" __Represent the model of the underlying application domain__"*
2. *"__The way the model is presented to the user__"*
3. *"__The way the user interacts with it__"*

Put another way, by Martin Fowler, the MVC approach is:
I. **Separation between UI and model** (steps 1 & 2)
II. **Divide UI into a 'controller' and a 'view'** (steps 2 & 3)
II. **Views are synchronized with model** (by means of a data binding mechanism)

### The Model

>  "The MVC _metaphor_, allows developers to write an application model by first defining new classes that __would embody the special application domain-specific information__"

From an architectural point of view, it is important to keep the app's model classes independent of

1. **the user interface (UI) code because it should be possible to re-use the same model classes with different UI technologies**
2. **the storage management code because it should be possible to re-use the same model classes with different storage technologies**
