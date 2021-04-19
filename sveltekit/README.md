# sveltekit sample

i tried

1. `npm init svelte@next sveltekit` (select `skelton`)
2. edit `index.svelte`, `test.js`(, `.gitignore`)
3. `npm run dev`
4. Error has occured!

```log
❯ npm run dev

> ~TODO~@0.0.1 dev C:\Dev\sveltekit-module-import-issue\sveltekit
> svelte-kit dev



  SvelteKit v1.0.0-next.83

  network: not exposed
  local:   http://localhost:3000

  Use --host to expose server to other devices on this network


14:56:47 [vite] Error when evaluating SSR module C:\Dev\sveltekit-module-import-issue\sveltekit\src\routes\index.svelte:
SyntaxError: Unexpected token '.'
    at new Function (<anonymous>)
    at instantiateModule (C:\Dev\sveltekit-module-import-issue\sveltekit\node_modules\vite\dist\node\chunks\dep-66eb515d.js:69030:9)
Unexpected token '.'
SyntaxError: Unexpected token '.'
    at new Function (<anonymous>)
    at instantiateModule (C:\Dev\sveltekit-module-import-issue\sveltekit\node_modules\vite\dist\node\chunks\dep-66eb515d.js:69030:9)
```
