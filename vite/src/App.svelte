<script context="module">
	import { hello } from './test';
</script>
<script>
	export let hello = 'world';
</script>
<!-- It shows "Hello svelte" -->
<h1>Hello {hello}</h1>
