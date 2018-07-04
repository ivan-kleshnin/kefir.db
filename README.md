# Kefir DB

**WIP**. High-level reactive states for [Kefir](kefirjs.github.io/kefir) stream library.

#### Short description

Unlike many others stream implementations, Kefir does have a *stateful stream* concept called `Property`.
Still this concept is very low-level and basic, without a functionality we typically expect from
an app-level reactive state. This library is based on native `Propery`, adding a number of additional features
and, most importantly, establishing an API for pluggable middlewares.

## Usage

```
$ npm install kefir.db
```

```js
import K from "kefir"
import * as D from "kefir.db"

let inc = (x) => x + 1
let dec = (x) => x - 1

let action$ = K.merge([
  K.constant(() => 0), // initial counter
  K.later(100, inc),   // increment counter after 100ms
  K.later(200, dec),   // decrement counter after 200ms
  K.later(300, inc),   // increment counter after 300ms
])

let Store = D.makeStore({})    // pass some options, check `makeStore.options` or docs
let state$ = Store(action$).$ // make state, getting stream from a `Store(..)` call

state$.log("state$")          // use built-in Kefir logging
// state$: 0--1--0--1-->
```

## Tutorials

#### [1. State](./tutorials/1.state)

Getting started with reactive states.

#### [2. Store](./tutorials/2.store)

Let's make a better store abstraction.

#### [10. Logging](./tutorials/10.log)

Learn how to use `Logging` middleware.

#### [11. Control](./tutorials/11.control)

Learn how to use `Control` middleware.

## Links

* [Kefir](https://kefirjs.github.io/kefir) (docs)
* [Reactive states](https://github.com/ivan-kleshnin/reactive-states) (article)
* [Unredux Project](https://github.com/ivan-kleshnin/unredux) (repo)
