<script lang="ts">
	const links = [
		{ name: 'Home', href: '#home', active: true },
		{ name: 'Work', href: '#work', active: false },
		{ name: 'About', href: '#about', active: false },
		{ name: 'Contact', href: '#contact', active: false }
	];
</script>
<nav
	class="fixed left-1/2 top-3 z-50 flex h-12 w-[70%] max-w-3xl -translate-x-1/2 items-center justify-between rounded-full border border-white/50 bg-white/35 px-5 backdrop-blur-2xl shadow-[0_12px_40px_rgba(0,0,0,0.07)] transition-all duration-300"
>
	<!-- Logo -->

	<a href="#home" class="flex items-center">
		<img
			src="/signature.png"
			alt="Amna Amjad"
			class="h-8 object-contain transition-transform duration-300 hover:scale-105"
		/>
	</a>

	<!-- Navigation -->

	<ul class="flex items-center gap-1">
		{#each links as link}
			<li>
				<a
					href={link.href}
					class={`rounded-full px-4 py-1.5 text-xs font-medium transition-all duration-300 ${
						link.active
							? 'bg-white text-black shadow-sm'
							: 'text-gray-600 hover:bg-white/70 hover:text-black'
					}`}
				>
					{link.name}
				</a>
			</li>
		{/each}
	</ul>

	<!-- CTA -->

	<button
		class="group flex items-center gap-1.5 rounded-full bg-black px-4 py-2 text-[11px] font-semibold tracking-wide text-white transition-all duration-300 hover:-translate-y-0.5 hover:scale-105 hover:bg-neutral-900 hover:shadow-[0_10px_25px_rgba(0,0,0,0.2)]"
	>
		HIRE ME

		<svg
			class="h-3.5 w-3.5 transition-transform duration-300 group-hover:translate-x-1"
			viewBox="0 0 24 24"
			fill="none"
			stroke="currentColor"
			stroke-width="2"
			stroke-linecap="round"
			stroke-linejoin="round"
		>
			<path d="M5 12h14" />
			<path d="m13 5 7 7-7 7" />
		</svg>
	</button>
</nav>