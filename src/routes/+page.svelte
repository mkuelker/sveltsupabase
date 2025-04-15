<script lang="ts">
	let autoMode = true;

	function toggleAuto() {
		autoMode = !autoMode;
	}
</script>

<main class="min-h-screen bg-[#0e1a2b] text-white p-6 flex gap-4">
	<!-- Sidebar -->
	<aside class="w-56 bg-[#13233a] p-4 rounded-lg">
		<h2 class="text-lg font-bold mb-4">Nonsense Panel</h2>
		<ul class="space-y-2">
			{#each ['Outside Chaos', 'Mood Beams', 'Peeping Orbs', 'Wi-Fi Prayers', 'Button Mashing Machines'] as item}
				<li>
					<button class="w-full text-left px-4 py-2 rounded-md bg-[#1a2e4a] hover:bg-blue-600 hover:text-white transition">
						{item}
					</button>
				</li>
			{/each}
		</ul>
	</aside>

	<!-- Main Content -->
	<section class="flex-1 flex flex-col gap-4">
		<!-- Device Grid -->
		<div class="grid grid-cols-3 gap-4 bg-[#13233a] p-4 rounded-lg">
			{#each [
				{ name: 'Entrance Cam', status: 'Judging visitors' },
				{ name: 'Garage Door', status: 'Probably closed?' },
				{ name: 'Garden Lights', status: 'Scaring raccoons' },
				{ name: 'Canopies', status: 'Doing nothing again' },
				{ name: 'Stairs Cam', status: 'Off. Definitely not haunted.' },
				{ name: 'Parasols', status: 'Deflecting zero sun' }
			] as device}
				<div class="bg-[#1a2e4a] rounded-md p-4 hover:text-blue-400 transition cursor-pointer border border-transparent hover:border-blue-400">
					<p class="text-lg font-semibold">{device.name}</p>
					<p class="text-sm text-gray-400 italic">{device.status}</p>
				</div>
			{/each}
		</div>

		<!-- General Commands -->
		<div class="bg-[#13233a] p-4 rounded-lg">
			<div class="flex items-center justify-between">
				<p class="text-xl">
					Thermostat: <span class="font-bold">25°C</span> – dangerously close to comfy
				</p>
				<button
					on:click={toggleAuto}
					class="bg-blue-600 px-4 py-2 rounded-full hover:bg-blue-500 transition"
				>
					{autoMode ? 'SkyNet Mode: ON' : 'Manual Mayhem'}
				</button>
			</div>
			<p class="mt-2 text-sm text-blue-300">
				Auto-regulation is currently {autoMode ? 'plotting behind your back' : 'too tired to care'}
			</p>
		</div>
	</section>
</main>
