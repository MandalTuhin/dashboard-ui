<!-- Revenue Section with Metrics and Cards -->
<script>
	// Revenue metrics data
	const revenueData = {
		total: '$528,976.82',
		change: '-7.9%',
		changeAmount: '$27,335.09',
		previousPeriod: 'vs prev. $501,641.73',
		dateRange: 'Jun 1 - Aug 31, 2023'
	};

	const topSales = {
		value: '72',
		company: 'Mikasa'
	};

	const bestDeal = {
		company: 'Rolf Inc.',
		starred: true
	};

	const metrics = [
		{ label: 'Deals', value: '5299', change: '+7.9%', positive: true },
		{ label: 'Value', value: '$288k', change: '+7.9%', positive: true },
		{ label: 'Win rate', value: '41%', change: '+1.2%', positive: true }
	];

	const salesReps = [
		{ name: 'Armin A.', amount: '$209,633', percentage: '39.63%' },
		{ name: 'Mikasa A.', amount: '$156,841', percentage: '29.65%' },
		{ name: 'Eren Y.', amount: '$117,115', percentage: '22.14%' },
		{ name: 'Other', amount: '$45,386', percentage: '8.58%' }
	];
</script>

<section class="space-y-6">
	<!-- Revenue Header -->
	<div class="flex items-center justify-between">
		<div>
			<h2 class="text-lg font-semibold text-gray-900 mb-1">Revenue</h2>
			<div class="flex items-center space-x-4 text-sm text-gray-600">
				<span>{revenueData.previousPeriod}</span>
				<span>{revenueData.dateRange}</span>
				<div class="w-3 h-3 bg-gray-400 rounded-sm"></div>
			</div>
		</div>
		
		<div class="flex items-center space-x-4">
			<!-- Timeframe Toggle -->
			<div class="flex items-center space-x-2">
				<span class="text-sm text-gray-600">Timeframe</span>
				<div class="w-8 h-4 bg-gray-300 rounded-full relative">
					<div class="w-3 h-3 bg-white rounded-full absolute top-0.5 right-0.5 shadow-sm"></div>
				</div>
			</div>
			
			<!-- Date Range -->
			<div class="flex items-center space-x-2 text-sm text-gray-600">
				<span>Sep 1 - Nov 30, 2023</span>
				<div class="w-3 h-3 bg-gray-400 rounded-sm"></div>
			</div>
		</div>
	</div>

	<!-- Main Revenue Display -->
	<div class="flex items-center space-x-6">
		<div>
			<div class="text-4xl font-light text-gray-900">{revenueData.total}</div>
			<div class="flex items-center space-x-2 mt-1">
				<span class="text-red-500 text-sm">{revenueData.change}</span>
				<span class="text-red-500 text-sm">{revenueData.changeAmount}</span>
			</div>
		</div>
	</div>

	<!-- Cards Row -->
	<div class="flex items-center space-x-4">
		<!-- Top Sales Card -->
		<div class="card p-4 min-w-[120px]">
			<div class="text-xs text-gray-500 mb-1">Top sales</div>
			<div class="text-2xl font-semibold text-gray-900 mb-2">{topSales.value}</div>
			<div class="flex items-center space-x-2">
				<div class="profile-pic w-6 h-6"></div>
				<span class="text-sm text-gray-600">{topSales.company}</span>
				<div class="w-3 h-3 bg-gray-400 rounded-sm"></div>
			</div>
		</div>

		<!-- Best Deal Card -->
		<div class="card p-4 min-w-[120px] bg-gray-900 text-white">
			<div class="flex items-center justify-between mb-2">
				<span class="text-xs text-gray-300">Best deal</span>
				<div class="w-3 h-3 bg-yellow-400 rounded-sm"></div>
			</div>
			<div class="text-sm font-medium">{bestDeal.company}</div>
			<div class="w-4 h-4 bg-white rounded-full mt-2"></div>
		</div>

		<!-- Metrics Cards -->
		{#each metrics as metric}
			<div class="card p-4 min-w-[100px]">
				<div class="text-xs text-gray-500 mb-1">{metric.label}</div>
				<div class="text-lg font-semibold text-gray-900 mb-1">{metric.value}</div>
				<div class="text-xs text-green-600">{metric.change}</div>
			</div>
		{/each}
	</div>

	<!-- Sales Representatives -->
	<div class="flex items-center space-x-8">
		{#each salesReps as rep}
			<div class="flex items-center space-x-3">
				<div class="profile-pic w-8 h-8"></div>
				<div>
					<div class="text-sm font-medium text-gray-900">{rep.amount}</div>
					<div class="text-xs text-gray-500">{rep.percentage}</div>
				</div>
			</div>
		{/each}
		
		<span class="bg-gray-900 text-white px-3 py-1 rounded text-sm">Details</span>
	</div>
</section>
