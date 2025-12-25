<!-- Sidebar Navigation Component -->
<script>
	// Sidebar navigation items
	const navigationItems = [
		{ name: 'Starred', active: false },
		{ name: 'Recent', active: false },
		{ name: 'Sales list', active: false },
		{ name: 'Goals', active: false },
		{ name: 'Dashboard', active: true },
		{ name: 'Codename', active: false },
		{ name: 'Shared with me', active: false },
		{ name: 'CargoZoo', active: false },
		{ name: 'Cloud3r', active: false, hasNotification: true },
		{ name: 'Idioma', active: false },
		{ name: 'Syllables', active: false },
		{ name: 'Db', active: false }
	];

	const reportItems = [
		{ name: 'Share with me', active: false },
		{ name: 'Deals by user', active: false },
		{ name: 'Deal duration', active: false },
		{ name: 'My reports', active: false },
		{ name: 'Emails received', active: false },
		{ name: 'Deal duration', active: false },
		{ name: 'New report', active: false, isNew: true },
		{ name: 'Analytics', active: false, hasNotification: true }
	];
</script>

<div class="flex w-64 flex-col border-r border-gray-200 bg-white">
	<!-- Logo Section -->
	<div class="border-b border-gray-200 p-4">
		<div class="flex items-center space-x-2">
			<div class="flex h-8 w-8 items-center justify-center rounded-full bg-black">
				<span class="text-sm font-bold text-white">A</span>
			</div>
			<span class="font-semibold text-gray-900">Codename.com</span>
			<div class="ml-auto h-3 w-3 rounded-sm bg-gray-400"></div>
		</div>
	</div>

	<!-- Navigation Section -->
	<div class="flex-1 overflow-y-auto p-4">
		<!-- Main Navigation -->
		<nav class="mb-6 space-y-1">
			{#each navigationItems as item}
				<div class="sidebar-item {item.active ? 'active' : ''}">
					<div class="mr-3 h-4 w-4 rounded-sm bg-gray-400"></div>
					<span class="flex-1">{item.name}</span>
					{#if item.hasNotification}
						<div class="h-2 w-2 rounded-full bg-red-500"></div>
					{/if}
					{#if item.name === 'Dashboard'}
						<div class="ml-2 h-3 w-3 rounded-sm bg-gray-400"></div>
					{/if}
				</div>
			{/each}
		</nav>

		<!-- Reports Section -->
		<div class="border-t border-gray-200 pt-4">
			<div class="mb-3 flex items-center justify-between">
				<span class="text-sm font-medium text-gray-900">Reports</span>
				<div class="h-3 w-3 rounded-sm bg-gray-400"></div>
			</div>
			<nav class="space-y-1">
				{#each reportItems as item}
					<div class="sidebar-item {item.active ? 'active' : ''}">
						<div class="mr-3 h-4 w-4 rounded-sm bg-gray-400"></div>
						<span class="flex-1 {item.isNew ? 'text-red-500' : ''}">{item.name}</span>
						{#if item.hasNotification}
							<div class="h-2 w-2 rounded-full bg-red-500"></div>
						{/if}
					</div>
				{/each}
			</nav>
		</div>

		<!-- Manage Folders -->
		<div class="mt-6 border-t border-gray-200 pt-4">
			<div class="sidebar-item">
				<div class="mr-3 h-4 w-4 rounded-sm bg-gray-400"></div>
				<span class="text-sm text-gray-600">Manage folders</span>
			</div>
		</div>
	</div>

	<!-- Bottom Icons -->
	<div class="space-y-4 border-t border-gray-200 p-4">
		<div class="h-6 w-6 rounded-sm bg-gray-400"></div>
		<div class="h-6 w-6 rounded-sm bg-gray-400"></div>
	</div>
</div>
