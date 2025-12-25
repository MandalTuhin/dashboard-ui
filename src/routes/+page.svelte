<!-- Dashboard Main Page -->
<script>
	import Sidebar from '$lib/components/Sidebar.svelte';
	import Header from '$lib/components/Header.svelte';
	import MainContent from '$lib/components/MainContent.svelte';
</script>

<div class="flex h-screen bg-gray-50">
	<!-- Sidebar -->
	<Sidebar />
	
	<!-- Main Content Area -->
	<div class="flex-1 flex flex-col overflow-hidden">
		<!-- Header -->
		<Header />
		
		<!-- Main Content -->
		<MainContent />
	</div>
</div>
