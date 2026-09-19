<script lang="ts">
	import Navbar from '$lib/components/Navbar.svelte';
	import '../app.css';
	let { children } = $props();
</script>

<svelte:head>
	<title>Amna Amjad | Full Stack Developer</title>
	<meta
		name="description"
		content="Amna Amjad — Full Stack Developer building modern web experiences."
	/>
</svelte:head>


<!-- Global Background -->

<div class="pointer-events-none fixed inset-0 -z-10">

	<!-- Vignette -->

	<div
		class="absolute inset-0"
		style="
			background:
				radial-gradient(
					circle at center,
					transparent 50%,
					rgba(0,0,0,.06)
				);
		"
	></div>


	<!-- Grid -->

	<div
		class="absolute inset-0 opacity-[0.025]"
		style="
			background-image:
				linear-gradient(to right,#000 1px,transparent 1px),
				linear-gradient(to bottom,#000 1px,transparent 1px);
			background-size: 60px 60px;
		"
	></div>


	<!-- Grain -->

	<div
		class="absolute inset-0 opacity-[0.04]"
		style="
			background-image:
				radial-gradient(#000 0.4px, transparent 0.4px);
			background-size: 5px 5px;
		"
	></div>


	<!-- Center Glow -->

	<div
		class="absolute left-1/2 top-1/2 h-[700px] w-[700px]
			-translate-x-1/2 -translate-y-1/2
			rounded-full bg-amber-100/30 blur-[130px]"
	></div>


	<!-- Pink Blob -->

	<div
		class="absolute -left-32 top-20 h-96 w-96
			rounded-full bg-pink-500/20 blur-[120px]"
	></div>


	<!-- Cyan Blob -->

	<div
		class="absolute -right-32 top-[55%] h-96 w-96
			rounded-full bg-cyan-500/20 blur-[120px]"
	></div>

</div>


<!-- Global Navbar -->

<Navbar />


<!-- Page Content -->

<div class="relative  pt-5">
	{@render children()}
</div>