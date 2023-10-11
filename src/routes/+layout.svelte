<script>
	import '../app.postcss';
	import Navbar from './navbar/+page.svelte';
	import Sidebar from './sidebar/+page.svelte';
</script>

<div class="navbar"><Navbar /></div>
<div class="sidebar"><Sidebar /></div>

<slot />
