<script context="module">
  const hello = 'svelte';
</script>

<script>
  export let hello = 'world';
</script>

<!-- This shows `Hello world` -->
<h1>Hello {hello}</h1>
