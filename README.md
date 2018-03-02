# Kefir DB

**WIP**. High-level reactive states for [Kefir](kefirjs.github.io/kefir) streaming toolkit.

#### Short description

Unlike many others reactive stream implementations, Kefir has a *stateful stream* concept called `Property`.
Still this concept is very low-level and basic and does not provide functionality we typically expect from
an app-level state. This library is based on native `Propery`, adding a number of additional features
and, most importantly, establishing an API for pluggable middlewares.

## Tutorials

#### [1. State](./tutorials/1.state)

Getting started with reactive states.

#### [2. Store](./tutorials/2.store)

Let's make a better store abstraction.

#### [10. Logging](./tutorials/10.log)

Learn how to use `Logging` middleware.

#### [11. Control](./tutorials/11.control)

Learn how to use `Control` middleware.
