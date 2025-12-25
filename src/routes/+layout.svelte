<!-- Main layout for the dashboard application -->
<script>
	import './layout.css';
</script>

<main class="min-h-screen bg-gray-50">
	<slot />
</main>

<style>
	/* Global styles for the dashboard */
	:global(body) {
		margin: 0;
		padding: 0;
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
	}
</style>
