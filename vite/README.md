# vite sample

i tried

1. `npm init @vitejs/app` (select `svelte`, `javascript`)
2. `npm i`
3. edit `App.svelte`, `test.js`
4. `npm run dev`
5. Error has occured!

```log
❯ npm run dev

> vite@0.0.0 dev
> vite

 > html:/Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/src/App.svelte:5:12: error: "hello" has already been declared
    5 │   export let hello = 'world';
      ╵              ~~~~~
   html:/Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/src/App.svelte:2:10: note: "hello" was originally declared here
    2 │   import { hello } from './test';
      ╵            ~~~~~

error when starting dev server:
Error: Build failed with 1 error:
html:/Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/src/App.svelte:5:12: error: "hello" has already been declared
    at failureErrorWithLog (/Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/node_modules/esbuild/lib/main.js:1224:15)
    at buildResponseToResult (/Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/node_modules/esbuild/lib/main.js:936:32)
    at /Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/node_modules/esbuild/lib/main.js:1035:20
    at /Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/node_modules/esbuild/lib/main.js:568:9
    at handleIncomingPacket (/Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/node_modules/esbuild/lib/main.js:657:9)
    at Socket.readFromStdout (/Users/sotaro/Dev/trainings/sveltekit-module-import-issue/vite/node_modules/esbuild/lib/main.js:535:7)
    at Socket.emit (node:events:378:20)
    at addChunk (node:internal/streams/readable:313:12)
    at readableAddChunk (node:internal/streams/readable:288:9)
    at Socket.Readable.push (node:internal/streams/readable:227:10)
```
