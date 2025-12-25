<!-- Main Content Area -->
<script>
	import RevenueSection from './RevenueSection.svelte';
	import DataTable from './DataTable.svelte';
	import ChartsSection from './ChartsSection.svelte';
</script>

<main class="flex-1 overflow-y-auto p-6">
	<div class="max-w-7xl mx-auto">
		<!-- Page Header -->
		<div class="flex items-center justify-between mb-6">
			<div class="flex items-center space-x-4">
				<div class="w-4 h-4 bg-gray-400 rounded-sm"></div>
				<div class="flex items-center space-x-2">
					<div class="profile-pic"></div>
					<span class="text-sm text-gray-600">Tuhin</span>
				</div>
				<div class="flex items-center space-x-2">
					<div class="profile-pic"></div>
					<span class="text-sm text-gray-600">Ramesh</span>
				</div>
				<div class="flex items-center space-x-2">
					<div class="profile-pic"></div>
					<span class="text-sm text-gray-600">Kiro</span>
				</div>
				<div class="w-6 h-6 bg-gray-400 rounded-sm"></div>
			</div>

			<div class="flex items-center space-x-3">
				<div class="w-5 h-5 bg-gray-400 rounded-sm"></div>
				<div class="w-5 h-5 bg-gray-400 rounded-sm"></div>
				<div class="w-5 h-5 bg-gray-400 rounded-sm"></div>
			</div>
		</div>

		<!-- New Report Title -->
		<h1 class="text-2xl font-light text-gray-400 mb-6">New report</h1>

		<!-- Revenue Section -->
		<RevenueSection />

		<!-- Data Tables and Charts -->
		<div class="grid grid-cols-1 lg:grid-cols-2 gap-6 mt-6">
			<DataTable />
			<ChartsSection />
		</div>
	</div>
</main>
