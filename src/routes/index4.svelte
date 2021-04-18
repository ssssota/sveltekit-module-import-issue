<script context="module" lang="ts">
  import type { Load } from "@sveltejs/kit";
  import { hello } from '$lib/test';

  export const load: Load = () => {
    return {
      props: {
        hello,
      },
    };
  };
</script>

<script>
  export let hello = 'world';
</script>

<h1>Hello {hello}</h1>
