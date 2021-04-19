# Cannot import that has same name props on the page file

- [Svelte sample](./svelte/README.md)
  - Work!
- [Sapper sample](./sapper/README.md)
  - Work!
- [Vite(Svelte) sample](./vite/README.md)
  - Error with clear message
- [SveltKit sample](./sveltekit/README.md)
  - Error with unfriendly message

## usage

### setup

```sh
cd sveltekit
pnpm i # npm i
```

### launch

```sh
pnpm dev # npm run dev
```

### you can see...

Access

- http://localhost:3000/  `basic example`
- http://localhost:3000/index2  `child can import`
- http://localhost:3000/index4  `load function`

```log
❯ pnpm dev

> ~TODO~@0.0.1 dev D:\Dev\trainings\sveltekit-test3
> svelte-kit dev

(node:10468) ExperimentalWarning: The ESM module loader is experimental.

  SvelteKit v1.0.0-next.80

  network: not exposed
  local:   http://localhost:3000
  network: not exposed

  Use --host to expose server to other devices on this network


1:59:08 [vite] Error when evaluating SSR module D:\Dev\trainings\sveltekit-test3\src\routes\index4.svelte:
SyntaxError: Unexpected token '.'
    at new Function (<anonymous>)
    at instantiateModule (D:\Dev\trainings\sveltekit-test3\node_modules\.pnpm\vite@2.1.5\node_modules\vite\dist\node\chunks\dep-66eb515d.js:69030:9)
Unexpected token '.'
SyntaxError: Unexpected token '.'
    at new Function (<anonymous>)
    at instantiateModule (D:\Dev\trainings\sveltekit-test3\node_modules\.pnpm\vite@2.1.5\node_modules\vite\dist\node\chunks\dep-66eb515d.js:69030:9)

```

## Issue

https://github.com/sveltejs/kit/issues/1108

> **Describe the bug**
> Error has occured if you tried import that has same name props in the page file.
> 
> e.g.
> *src/routes/index.svelte*
> ```svelte
> <script context="module">
>   import { hello } from '$lib/test'; // <- this import
> </script>
> 
> <script>
>   export let hello = '';
> </script>
> 
> <h1>Hello {hello}</h1>
> ```
> *src/lib/test.js*
> ```js
> export const hello = 'svelte';
> ```
> 
> **Logs**
> ```
> ❯ pnpm dev
> 
> > ~TODO~@0.0.1 dev D:\Dev\trainings\sveltekit-test3
> > svelte-kit dev
> 
> (node:18392) ExperimentalWarning: The ESM module loader is experimental.
> 
>   SvelteKit v1.0.0-next.80
> 
>   network: not exposed
>   local:   http://localhost:3000
>   network: not exposed
> 
>   Use --host to expose server to other devices on this network
> 
> 
> 1:31:15 [vite] Error when evaluating SSR module /src/lib/components/Child.svelte:
> SyntaxError: Unexpected token '.'
>     at new Function (<anonymous>)
>     at instantiateModule (D:\Dev\trainings\sveltekit-test3\node_modules\.pnpm\vite@2.1.5\node_modules\vite\dist\node\chunks\dep-66eb515d.js:69030:9)
> Unexpected token '.'
> SyntaxError: Unexpected token '.'
>     at new Function (<anonymous>)
>     at instantiateModule (D:\Dev\trainings\sveltekit-test3\node_modules\.pnpm\vite@2.1.5\node_modules\vite\dist\node\chunks\dep-66eb515d.js:69030:9)
> 
> ```
> 
> **To Reproduce**
> 
> 1. Create new SvelteKit project.
> 2. Fix `src/routes/index.svelte` and create `src/lib/test.ts` like above.
> 3. `pnpm dev`
> 
> reproduction repo -> https://github.com/ssssota/sveltekit-module-import-issue
> 
> This repo includes some samples.
> 
> **Expected behavior**
> 
> We will be able to import like above.
> And browser shows *Hello svelte*.
> 
> **Stacktraces**
> No stacktraces.
> 
> **Information about your SvelteKit Installation:**
> 
> <details>
>   <summary>Diagnostics</summary>
> 
>   System:
>     OS: Windows 10 10.0.19042
>     CPU: (12) x64 AMD Ryzen 5 2600 Six-Core Processor
>     Memory: 5.08 GB / 15.93 GB
>   Binaries:
>     Node: 12.19.0 - C:\Program Files\nodejs\node.EXE
>     npm: 7.9.0 - C:\Program Files\nodejs\npm.CMD
>   Browsers:
>     Chrome: 89.0.4389.114
>     Edge: Spartan (44.19041.906.0), Chromium (89.0.774.77)
>     Internet Explorer: 11.0.19041.1
>   npmPackages:
>     @sveltejs/adapter-node: next => 1.0.0-next.15
>     @sveltejs/kit: next => 1.0.0-next.80
>     svelte: ^3.29.0 => 3.37.0
>     vite: ^2.1.0 => 2.1.5
> 
> </details>
> 
> **Severity**
> 1. Severe - I can't read the cause from the logs.
> 2. Normal - We should be able to import that.
> 
