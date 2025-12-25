<!-- Header Component with Search and User Profile -->
<script>
	// User avatars data
	const users = [
		{ name: 'Tuhin', initials: 'T' },
		{ name: 'Ramesh', initials: 'R' },
		{ name: 'Kiro', initials: 'K' }
	];
</script>

<header class="bg-white border-b border-gray-200 px-6 py-4">
	<div class="flex items-center justify-between">
		<!-- Search Section -->
		<div class="flex-1 max-w-md">
			<div class="relative">
				<div class="absolute inset-y-0 left-0 pl-3 flex items-center">
					<div class="w-4 h-4 bg-gray-400 rounded-sm"></div>
				</div>
				<input
					type="text"
					placeholder="Try searching 'insights'"
					class="w-full pl-10 pr-4 py-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent text-sm"
				/>
			</div>
		</div>

		<!-- Right Section -->
		<div class="flex items-center space-x-4">
			<!-- User Avatars -->
			<div class="flex items-center space-x-2">
				<div class="w-4 h-4 bg-gray-400 rounded-sm"></div>
				{#each users as user}
					<div class="profile-pic"></div>
				{/each}
				<div class="w-6 h-6 bg-gray-400 rounded-sm"></div>
			</div>

			<!-- Menu and Profile -->
			<div class="flex items-center space-x-3">
				<div class="w-5 h-5 bg-gray-400 rounded-sm"></div>
				<div class="profile-pic"></div>
				<div class="w-8 h-8 bg-pink-500 rounded-full flex items-center justify-center">
					<div class="w-4 h-4 bg-white rounded-sm"></div>
				</div>
			</div>
		</div>
	</div>
</header>
