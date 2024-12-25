<script lang="ts">
	import wheel from '../assets/wheel.png';
	import { onMount } from 'svelte';

	let rotation = 0;
	const SPEED = 0.1;

	onMount(() => {
		const animate = () => {
			rotation += SPEED;
			requestAnimationFrame(animate);
		};
		animate();
	});
</script>

<div class="flex h-screen flex-col">
	<div class="grid grid-cols-4 border-black p-4">
		<div class="col-span-3 flex items-start justify-start border-8 border-r-0 border-black">
			<h1 class="p-6 text-6xl">fhonk</h1>
		</div>
		<div
			class="col-span-1 flex items-center justify-center border-8 border-black transition hover:-translate-y-2 hover:translate-x-2 hover:bg-black hover:text-[#D6FFD6]"
		>
			<span class="text-xl">Coming Soon.</span>
		</div>
	</div>
	<div class="flex flex-grow flex-col items-center justify-center">
		<h1 class="text-6xl">fhonk</h1>
		<p>some caption here</p>
	</div>
</div>

<div class="fixed bottom-0 right-0 overflow-hidden">
	<img
		src={wheel}
		alt="wheel"
		class="translate-x-1/2 translate-y-1/2 object-fill"
		style="transform: translate(50%, 50%) rotate({rotation}deg)"
		id="wheel"
	/>
</div>
