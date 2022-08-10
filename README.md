# projetoGitES
Projeto para a Graduação de Engenharia da Computação 
# queue-microtask [![ci][ci-image]][ci-url] [![npm][npm-image]][npm-url] [![downloads][downloads-image]][downloads-url] [![javascript style guide][standard-image]][standard-url]

[ci-image]: https://img.shields.io/github/workflow/status/feross/queue-microtask/ci/master
[ci-url]: https://github.com/feross/queue-microtask/actions
[npm-image]: https://img.shields.io/npm/v/queue-microtask.svg
[npm-url]: https://npmjs.org/package/queue-microtask
[downloads-image]: https://img.shields.io/npm/dm/queue-microtask.svg
[downloads-url]: https://npmjs.org/package/queue-microtask
[standard-image]: https://img.shields.io/badge/code_style-standard-brightgreen.svg
[standard-url]: https://standardjs.com

### fast, tiny [`queueMicrotask`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask) shim for modern engines

- Use [`queueMicrotask`](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/queueMicrotask) in all modern JS engines.
- No dependencies. Less than 10 lines. No shims or complicated fallbacks.
- Optimal performance in all modern environments
  - Uses `queueMicrotask` in modern environments
  - Fallback to `Promise.resolve().then(fn)` in Node.js 10 and earlier, and old browsers (same performance as `queueMicrotask`)

## install

```
npm install queue-microtask
```

## usage

```js
const queueMicrotask = require('queue-microtask')

queueMicrotask(() => { /* this will run soon */ })
```

## What is `queueMicrotask` and why would one use it?

The `queueMicrotask` function is a WHATWG standard. It queues a microtask to be executed prior to control returning to the event loop.


See the [spec](https://html.spec.whatwg.org/multipage/timers-and-user-prompts.html#microtask-queuing) or [Node documentation](https://nodejs.org/api/globals.html#globals_queuemicrotask_callback) for more information.

