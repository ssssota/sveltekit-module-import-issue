<script context="module">
  // import { hello } from '$lib/test';
</script>

<script>
  import Child from '$lib/components/Child.svelte';
  export let hello = '';
</script>

<h1>Hello {hello}</h1>

<!-- Child components can import -->
<Child hello2="world" />
