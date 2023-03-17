# Web Standards

## Web Workers

Long-running code can slow down rendering in the browser. Therefore, there is a way to spawn supplementary worker processes in the browser called [Web Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers).
The processes cannot interact with the DOM or make network requests, but they can perform computation.
You can communicate with these processes via a message passing system (browser-created sort of IPC).

## CSPs and WASM

CSPs are a nice security feature for a site. Unfortunately they don't play well with WASM code, which the browser interprets as using `eval`.
There is a bleeding-edge standard in CSPs called `wasm-unsafe-eval` that doesn't seem to be documented anywhere except [this GitHub issue](https://github.com/w3c/webappsec-csp/pull/293) but currently works in latest Chrome (97).

## REST DELETE

According to a StackOverflow post clarifying an RFC, it is improper for a DELETE REST request to contain a body.

## Referrer and Opener for links

- Apparently, when a link spawns a new window or tab, that new window has some permissions on the parent.
To disable this, you should put `rel="noopener"` on your anchor tag.
- It's best to specify the `rel="noreferrer"` attribute on links as well.
- Both the link and script tag allow specifying the attribute `crossorigin="anonymous"` which will prevent accidentally sending credentials to a CDN.
- Both the link and script tags allow for specifying the attribute `referrerpolicy="no-referrer"` which will prevent our site from sending Referer info to a CDN
