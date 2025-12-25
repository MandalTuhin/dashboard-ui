<!-- Charts Section Component -->
<script>
	// Chart data for deals amount by referrer category
	const chartData = {
		percentage: '45.3%',
		amount: '$71,048',
		previousAmount: '$14,960'
	};

	// Sales dynamic chart data points
	const chartPoints = [
		{ x: 10, y: 40 },
		{ x: 20, y: 35 },
		{ x: 30, y: 45 },
		{ x: 40, y: 30 },
		{ x: 50, y: 50 },
		{ x: 60, y: 25 },
		{ x: 70, y: 40 },
		{ x: 80, y: 35 },
		{ x: 90, y: 45 }
	];

	// Generate SVG path for the chart
	function generatePath(points) {
		if (points.length === 0) return '';
		
		let path = `M ${points[0].x} ${points[0].y}`;
		for (let i = 1; i < points.length; i++) {
			path += ` L ${points[i].x} ${points[i].y}`;
		}
		return path;
	}

	const salesData = [
		{ name: 'Ramesh', amount: '$117,115', score: 22, rate: '84', conversion: '0.79', percentage: '32%', value: 15 }
	];
</script>

<div class="space-y-6">
	<!-- Deals Amount Chart -->
	<div class="card">
		<div class="p-4 border-b border-gray-200">
			<div class="flex items-center justify-between">
				<span class="text-sm text-gray-600">Deals amount by referrer category</span>
				<div class="w-4 h-4 bg-gray-400 rounded-sm"></div>
			</div>
		</div>
		
		<div class="p-4">
			<!-- Chart Area -->
			<div class="relative h-32 mb-4">
				<!-- Placeholder for chart visualization -->
				<div class="absolute inset-0 bg-gradient-to-r from-pink-100 to-pink-200 rounded">
					<div class="h-full flex items-end justify-center space-x-1 p-2">
						{#each Array(8) as _, i}
							<div class="bg-pink-500 rounded-t" style="height: {Math.random() * 60 + 20}%; width: 12px;"></div>
						{/each}
					</div>
				</div>
				
				<!-- Chart Labels -->
				<div class="absolute bottom-0 left-0 right-0 flex justify-between px-2 text-xs text-gray-500">
					<span>$116.95</span>
					<span>$9,208</span>
				</div>
			</div>
			
			<!-- Chart Metrics -->
			<div class="text-center">
				<div class="text-2xl font-light text-gray-900 mb-1">{chartData.percentage}</div>
				<div class="text-lg text-gray-600">{chartData.amount}</div>
				<div class="text-sm text-gray-500">{chartData.previousAmount}</div>
			</div>
			
			<!-- Revenue/Leads Toggle -->
			<div class="flex justify-center mt-4">
				<div class="flex bg-gray-100 rounded-lg p-1">
					<span class="bg-white px-3 py-1 rounded text-sm text-gray-900 shadow-sm">Revenue</span>
					<span class="px-3 py-1 text-sm text-gray-600">Leads</span>
					<span class="px-3 py-1 text-sm text-gray-600">M/L</span>
				</div>
			</div>
		</div>
	</div>

	<!-- Sales Dynamic Chart -->
	<div class="card">
		<div class="p-4 border-b border-gray-200">
			<div class="flex items-center justify-between">
				<h3 class="font-medium text-gray-900">Sales dynamic</h3>
				<div class="w-4 h-4 bg-gray-400 rounded-sm"></div>
			</div>
		</div>
		
		<div class="p-4">
			<!-- Line Chart -->
			<div class="relative h-24 mb-4">
				<svg class="w-full h-full" viewBox="0 0 100 60">
					<!-- Grid lines -->
					<defs>
						<pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse">
							<path d="M 10 0 L 0 0 0 10" fill="none" stroke="#f0f0f0" stroke-width="0.5"/>
						</pattern>
					</defs>
					<rect width="100" height="60" fill="url(#grid)" />
					
					<!-- Chart line -->
					<path 
						d={generatePath(chartPoints)} 
						fill="none" 
						stroke="#e91e63" 
						stroke-width="2"
					/>
					
					<!-- Data points -->
					{#each chartPoints as point}
						<circle cx={point.x} cy={point.y} r="2" fill="#e91e63" />
					{/each}
				</svg>
			</div>
			
			<!-- Chart Legend -->
			<div class="flex justify-between text-xs text-gray-500 mb-4">
				<span>W1</span>
				<span>W2</span>
				<span>W3</span>
				<span>W4</span>
				<span>W5</span>
			</div>
		</div>
	</div>

	<!-- Additional Sales Data -->
	<div class="card">
		<div class="overflow-x-auto">
			<table class="w-full">
				<tbody>
					{#each salesData as row}
						<tr class="table-row">
							<td class="px-4 py-3">
								<div class="flex items-center space-x-3">
									<div class="profile-pic w-8 h-8"></div>
									<span class="text-sm font-medium text-gray-900">{row.name}</span>
								</div>
							</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.amount}</td>
							<td class="px-4 py-3">
								<span class="bg-gray-800 text-white px-2 py-1 rounded text-xs">{row.score}</span>
							</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.rate}</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.conversion}</td>
							<td class="px-4 py-3 text-sm text-gray-900">{row.percentage}</td>
							<td class="px-4 py-3">
								<span class="bg-gray-800 text-white px-2 py-1 rounded text-xs">{row.value}</span>
							</td>
						</tr>
					{/each}
				</tbody>
			</table>
		</div>
	</div>
</div>
