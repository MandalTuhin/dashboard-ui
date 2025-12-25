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
		{ name: 'X-Db', active: false }
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

<div class="w-64 bg-white border-r border-gray-200 flex flex-col">
	<!-- Logo Section -->
	<div class="p-4 border-b border-gray-200">
		<div class="flex items-center space-x-2">
			<div class="w-8 h-8 bg-black rounded-full flex items-center justify-center">
				<span class="text-white text-sm font-bold">C</span>
			</div>
			<span class="font-semibold text-gray-900">Codename.com</span>
			<div class="w-3 h-3 bg-gray-400 rounded-sm ml-auto"></div>
		</div>
	</div>

	<!-- Navigation Section -->
	<div class="flex-1 overflow-y-auto p-4">
		<!-- Main Navigation -->
		<nav class="space-y-1 mb-6">
			{#each navigationItems as item}
				<div class="sidebar-item {item.active ? 'active' : ''}">
					<div class="w-4 h-4 bg-gray-400 rounded-sm mr-3"></div>
					<span class="flex-1">{item.name}</span>
					{#if item.hasNotification}
						<div class="w-2 h-2 bg-red-500 rounded-full"></div>
					{/if}
					{#if item.name === 'Dashboard'}
						<div class="w-3 h-3 bg-gray-400 rounded-sm ml-2"></div>
					{/if}
				</div>
			{/each}
		</nav>

		<!-- Reports Section -->
		<div class="border-t border-gray-200 pt-4">
			<div class="flex items-center justify-between mb-3">
				<span class="text-sm font-medium text-gray-900">Reports</span>
				<div class="w-3 h-3 bg-gray-400 rounded-sm"></div>
			</div>
			<nav class="space-y-1">
				{#each reportItems as item}
					<div class="sidebar-item {item.active ? 'active' : ''}">
						<div class="w-4 h-4 bg-gray-400 rounded-sm mr-3"></div>
						<span class="flex-1 {item.isNew ? 'text-red-500' : ''}">{item.name}</span>
						{#if item.hasNotification}
							<div class="w-2 h-2 bg-red-500 rounded-full"></div>
						{/if}
					</div>
				{/each}
			</nav>
		</div>

		<!-- Manage Folders -->
		<div class="border-t border-gray-200 pt-4 mt-6">
			<div class="sidebar-item">
				<div class="w-4 h-4 bg-gray-400 rounded-sm mr-3"></div>
				<span class="text-sm text-gray-600">Manage folders</span>
			</div>
		</div>
	</div>

	<!-- Bottom Icons -->
	<div class="p-4 border-t border-gray-200 space-y-4">
		<div class="w-6 h-6 bg-gray-400 rounded-sm"></div>
		<div class="w-6 h-6 bg-gray-400 rounded-sm"></div>
	</div>
</div>
