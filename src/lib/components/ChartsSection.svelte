<!-- Charts Section Component -->
<script>
	// Chart data for deals amount by referrer category
	const chartData = {
		percentage: '45.3%',
		amount: '$71,048',
		previousAmount: '$14,960'
	};

	// Sales dynamic chart data points (normalized for better display)
	const chartPoints = [
		{ x: 5, y: 15 },
		{ x: 15, y: 25 },
		{ x: 25, y: 10 },
		{ x: 35, y: 30 },
		{ x: 45, y: 20 },
		{ x: 55, y: 35 },
		{ x: 65, y: 15 },
		{ x: 75, y: 25 },
		{ x: 85, y: 30 },
		{ x: 95, y: 20 }
	];

	// Generate smooth SVG path for the chart
	function generatePath(points) {
		if (points.length === 0) return '';
		
		let path = `M ${points[0].x} ${points[0].y}`;
		
		// Create smooth curves using quadratic bezier curves
		for (let i = 1; i < points.length; i++) {
			const prevPoint = points[i - 1];
			const currentPoint = points[i];
			
			// Control point for smooth curve
			const controlX = (prevPoint.x + currentPoint.x) / 2;
			const controlY = prevPoint.y;
			
			path += ` Q ${controlX} ${controlY} ${currentPoint.x} ${currentPoint.y}`;
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
			<div class="relative h-32 mb-6 bg-gray-50 rounded-lg p-4">
				<svg class="w-full h-full" viewBox="0 0 100 40" preserveAspectRatio="none">
					<!-- Background grid -->
					<defs>
						<pattern id="grid" width="20" height="8" patternUnits="userSpaceOnUse">
							<path d="M 20 0 L 0 0 0 8" fill="none" stroke="#e5e7eb" stroke-width="0.5"/>
						</pattern>
					</defs>
					<rect width="100" height="40" fill="url(#grid)" />
					
					<!-- Chart area background -->
					<rect x="0" y="0" width="100" height="40" fill="rgba(233, 30, 99, 0.05)" />
					
					<!-- Chart line with gradient -->
					<defs>
						<linearGradient id="lineGradient" x1="0%" y1="0%" x2="100%" y2="0%">
							<stop offset="0%" style="stop-color:#e91e63;stop-opacity:1" />
							<stop offset="100%" style="stop-color:#ec4899;stop-opacity:1" />
						</linearGradient>
					</defs>
					
					<!-- Main chart line -->
					<path 
						d={generatePath(chartPoints)} 
						fill="none" 
						stroke="url(#lineGradient)" 
						stroke-width="2"
						stroke-linecap="round"
						stroke-linejoin="round"
					/>
					
					<!-- Data points -->
					{#each chartPoints as point, index}
						<circle 
							cx={point.x} 
							cy={point.y} 
							r="3" 
							fill="#ffffff" 
							stroke="#e91e63" 
							stroke-width="2"
						/>
						<!-- Hover area -->
						<circle 
							cx={point.x} 
							cy={point.y} 
							r="6" 
							fill="transparent" 
							class="cursor-pointer hover:fill-pink-100"
						/>
					{/each}
				</svg>
			</div>
			
			<!-- Chart Legend with better spacing -->
			<div class="flex justify-between items-center text-xs text-gray-500 mb-4 px-2">
				<span class="font-medium">W1</span>
				<span class="font-medium">W2</span>
				<span class="font-medium">W3</span>
				<span class="font-medium">W4</span>
				<span class="font-medium">W5</span>
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
