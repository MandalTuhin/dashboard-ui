<!-- Data Table Component -->
<script>
	// Table data
	const tableData = [
		{
			name: 'Armin A.',
			revenue: '$209,633',
			leads: 411,
			conversion: 118,
			rate: '0.84',
			percentage: '31%',
			score: 12,
			value: 29
		},
		{
			name: 'Mikasa A.',
			revenue: '$156,841',
			leads: 54,
			conversion: 103,
			rate: '0.89',
			percentage: '39%',
			score: 21,
			value: 33,
			hasIssue: true
		}
	];

	const platformData = [
		{ name: 'Dribbble', amount: '$227,459', percentage: '43%', color: 'bg-pink-500' },
		{ name: 'Instagram', amount: '$142,823', percentage: '27%', color: 'bg-purple-500' },
		{ name: 'Behance', amount: '$89,935', percentage: '17%', color: 'bg-blue-500' },
		{ name: 'Google', amount: '$37,028', percentage: '7%', color: 'bg-red-500' }
	];
</script>

<div class="space-y-6">
	<!-- Sales Performance Table -->
	<div class="card">
		<div class="p-4 border-b border-gray-200">
			<div class="flex items-center justify-between">
				<h3 class="font-medium text-gray-900">Sales</h3>
				<div class="flex items-center space-x-2">
					<span class="text-sm text-gray-600">Revenue</span>
					<span class="text-sm text-gray-600">Leads</span>
					<span class="text-sm text-gray-600">KPI</span>
					<span class="text-sm text-gray-600">W/L</span>
				</div>
			</div>
		</div>
		
		<div class="overflow-x-auto">
			<table class="w-full">
				<tbody>
					{#each tableData as row}
						<tr class="table-row">
							<td class="px-4 py-3">
								<div class="flex items-center space-x-3">
									<div class="profile-pic w-8 h-8"></div>
									<span class="text-sm font-medium text-gray-900">{row.name}</span>
								</div>
							</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.revenue}</td>
							<td class="px-4 py-3">
								<span class="bg-gray-100 text-gray-800 px-2 py-1 rounded text-xs">{row.leads}</span>
							</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.conversion}</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.rate}</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.percentage}</td>
							<td class="px-4 py-3">
								<span class="bg-gray-800 text-white px-2 py-1 rounded text-xs">{row.score}</span>
							</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.value}</td>
							{#if row.hasIssue}
								<td class="px-4 py-3">
									<div class="w-6 h-6 bg-red-500 rounded-full"></div>
								</td>
							{/if}
						</tr>
					{/each}
				</tbody>
			</table>
		</div>
	</div>

	<!-- Platform Performance -->
	<div class="card">
		<div class="p-4 border-b border-gray-200">
			<div class="flex items-center justify-between">
				<span class="text-sm text-gray-600">Filters</span>
				<div class="w-4 h-4 bg-gray-400 rounded-sm"></div>
			</div>
		</div>
		
		<div class="p-4 space-y-3">
			{#each platformData as platform}
				<div class="flex items-center justify-between">
					<div class="flex items-center space-x-3">
						<div class="w-6 h-6 {platform.color} rounded"></div>
						<span class="text-sm text-gray-900">{platform.name}</span>
					</div>
					<div class="flex items-center space-x-4">
						<span class="text-sm font-medium text-gray-900">{platform.amount}</span>
						<span class="text-sm text-gray-500">{platform.percentage}</span>
					</div>
				</div>
			{/each}
		</div>
	</div>

	<!-- Work with Platforms -->
	<div class="card">
		<div class="p-4 border-b border-gray-200">
			<h3 class="font-medium text-gray-900">Work with platforms</h3>
		</div>
		
		<div class="p-4">
			<div class="flex items-center justify-between mb-4">
				<div class="flex items-center space-x-2">
					<span class="text-orange-500 text-sm">Top sales 🔥</span>
					<span class="text-red-500 text-sm">Sales streak 🔥</span>
					<span class="text-orange-500 text-sm">Top review 🔥</span>
				</div>
			</div>
			
			<div class="space-y-3">
				<div class="flex items-center justify-between">
					<div class="flex items-center space-x-3">
						<div class="w-6 h-6 bg-pink-500 rounded"></div>
						<span class="text-sm text-gray-900">Dribbble</span>
					</div>
					<div class="flex items-center space-x-2">
						<span class="bg-pink-100 text-pink-800 px-2 py-1 rounded text-xs">$156,841</span>
					</div>
				</div>
				
				<div class="flex items-center justify-between">
					<div class="flex items-center space-x-3">
						<div class="w-6 h-6 bg-purple-500 rounded"></div>
						<span class="text-sm text-gray-900">Instagram</span>
					</div>
				</div>
				
				<div class="flex items-center justify-between">
					<div class="flex items-center space-x-3">
						<div class="w-6 h-6 bg-red-500 rounded"></div>
						<span class="text-sm text-gray-900">Google</span>
					</div>
					<span class="text-sm text-gray-500">14.1% $27,115</span>
				</div>
			</div>
			
			<div class="mt-4 pt-4 border-t border-gray-200">
				<div class="flex justify-between text-sm">
					<span class="text-gray-600">28.1% $94,072</span>
					<span class="text-gray-900 font-medium">5.4% $8,408</span>
				</div>
				
				<div class="mt-2">
					<span class="text-sm text-gray-600">Other</span>
					<span class="text-sm text-gray-500 ml-4">7.1% $41,135</span>
				</div>
			</div>
		</div>
	</div>
</div>
