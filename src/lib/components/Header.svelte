<!-- Header Component with Search and User Profile -->
<script>
	import { Plus } from 'phosphor-svelte';

	// User avatars data
	const users = [
		{ name: 'Tuhin', initials: 'T' },
		{ name: 'Ramesh', initials: 'R' },
		{ name: 'Kiro', initials: 'K' }
	];
</script>

<header class="border-b border-gray-200 bg-white px-6 py-4">
	<div class="flex items-center justify-between">
		<!-- Search Section -->
		<div class="max-w-md flex-1">
			<div class="relative">
				<div class="absolute inset-y-0 left-0 flex items-center pl-3">
					<Plus size={16} class="text-gray-600" />
				</div>
				<input
					type="text"
					placeholder="Try searching 'insights'"
					class="w-full rounded-lg border border-gray-300 py-2 pr-4 pl-10 text-sm focus:border-transparent focus:ring-2 focus:ring-blue-500"
				/>
			</div>
		</div>

		<!-- Right Section -->
		<div class="flex items-center space-x-4">
			<!-- User Avatars -->
			<div class="flex items-center space-x-2">
				<div class="h-4 w-4 rounded-sm bg-gray-400"></div>
				{#each users as user}
					<div class="profile-pic"></div>
				{/each}
				<div class="h-6 w-6 rounded-sm bg-gray-400"></div>
			</div>

			<!-- Menu and Profile -->
			<div class="flex items-center space-x-3">
				<div class="h-5 w-5 rounded-sm bg-gray-400"></div>
				<div class="profile-pic"></div>
				<div class="flex h-8 w-8 items-center justify-center rounded-full bg-pink-500">
					<div class="h-4 w-4 rounded-sm bg-white"></div>
				</div>
			</div>
		</div>
	</div>
</header>
