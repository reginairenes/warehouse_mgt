<script>
    import GridTable from '../table/+page.svelte';
</script>

<div class="flex px-4 mx-auto w-full">
	<main class="lg:ml-50 w-full mx-auto">
		<h1 class="self-center whitespace-nowrap text-xl font-semibold dark:text-dark mt-3 mb-4">
			Tracking List
		</h1>
		<GridTable/>
		<slot />
	</main>
</div>