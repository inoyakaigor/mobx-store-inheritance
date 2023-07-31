[![Mobx store inheritance](https://github.com/inoyakaigor/mobx-store-inheritance/actions/workflows/npm-publish.yml/badge.svg)](https://github.com/inoyakaigor/mobx-store-inheritance/actions/workflows/npm-publish.yml)

# What is this?
The `makeAutoObservable` function does not supporting subclassing. It is described in the Mobx [docs](https://mobx.js.org/subclassing.html#limitations).

This package fixes the issue with subclassing.


The code in this package is a slightly modified version from an [answer](https://github.com/mobxjs/mobx/discussions/2850#discussioncomment-497321) about inheritance in Mobx.

It has been tested in production on a few different projects.

# How to use?

It is easy: use makeAutoObservable in constructor of _inherited_ store.

```javascript
import makeAutoObservable from 'mobx-store-inheritance'

class BaseStore {
  theField = 1

  theMethod() {
    return this.theField
  }
}

class InheritedStore extends BaseStore {
  constructor() {
    makeAutoObservable(this)
  }

  theProperty = 'Ineritance is good'
}
```
