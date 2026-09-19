<script lang="ts">
	import Icon from '@iconify/svelte';

	const frontendStack = [
		{ name: 'React', icon: 'logos:react' },
		{ name: 'Next.js', icon: 'logos:nextjs-icon' },
		{ name: 'TypeScript', icon: 'logos:typescript-icon' },
		{ name: 'Tailwind CSS', icon: 'logos:tailwindcss-icon' },
		{ name: 'SvelteKit', icon: 'logos:svelte-kit' },
		{ name: 'GSAP', icon: 'logos:gsap' },
		{ name: 'Framer Motion', icon: 'logos:framer' },
		{ name: 'Zod', icon: 'simple-icons:zod' }
	];

	const backendStack = [
		{ name: 'Node.js', icon: 'logos:nodejs-icon' },
		{ name: 'NestJS', icon: 'logos:nestjs' },
		{ name: 'PostgreSQL', icon: 'logos:postgresql' },
		{ name: 'Prisma', icon: 'logos:prisma' },
		{ name: 'MongoDB', icon: 'logos:mongodb-icon' },
		{ name: 'Zustand', icon: 'simple-icons:zustand' },
		{ name: 'Git', icon: 'logos:git-icon' },
		{ name: 'Docker', icon: 'logos:docker-icon' }
	];

	// Duplicate the arrays so the ticker can loop seamlessly.
	const frontendTicker = [...frontendStack, ...frontendStack];
	const backendTicker = [...backendStack, ...backendStack];
</script>

<section
	id="tech-stack"
	class="relative flex min-h-screen w-full flex-col items-center justify-center overflow-hidden bg-transparent py-10"
>
	<!-- ========================= -->
	<!-- Background -->
	<!-- ========================= -->

	<div class="pointer-events-none absolute inset-0">
		
		<!-- Soft center glow -->

		<div
			class="absolute left-1/2 top-1/2 h-[500px] w-[500px]
				-translate-x-1/2 -translate-y-1/2
				rounded-full bg-amber-100/30 blur-[130px]"
		></div>
	</div>

	<!-- ========================= -->
	<!-- Section Heading -->
	<!-- ========================= -->

	<div class="relative z-10 mb-16 px-6 text-center">
		<p
			class="mb-5 text-xs font-medium uppercase tracking-[0.3em] text-black/45"
		>
			The Tools Behind The Work
		</p>

		<h2
			class="mx-auto max-w-4xl text-5xl font-semibold leading-[0.95]
				tracking-[-0.045em] text-black md:text-7xl lg:text-8xl"
		>
			I build with the tools that
			<span class="font-serif-display italic">
				turn ideas
			</span>
			into experiences.
		</h2>

		<p
			class="mx-auto mt-7 max-w-2xl text-sm leading-7 text-black/45 md:text-base"
		>
			A constantly evolving toolkit for building fast, thoughtful,
			and scalable digital products.
		</p>
	</div>

	<!-- ========================= -->
	<!-- TICKER AREA -->
	<!-- ========================= -->

	<div class="relative z-10 w-full space-y-2">
		<!-- Edge fade -->

		<div
			class="pointer-events-none absolute inset-y-0 left-0 z-20 w-32
				bg-gradient-to-r from-white to-transparent"
		></div>

		<div
			class="pointer-events-none absolute inset-y-0 right-0 z-20 w-32
				bg-gradient-to-l from-white to-transparent"
		></div>

		<!-- ========================= -->
		<!-- FRONTEND TICKER -->
		<!-- ========================= -->

		<div
			class="ticker-wrapper overflow-hidden border-y border-black/10
				bg-white/55 py-3 backdrop-blur-xl"
		>
			<div class="ticker ticker-left flex w-max items-center">
				{#each frontendTicker as tech}
					<div
						class="tech-item group mx-3 flex items-center gap-3
							rounded-full border border-black/8
							bg-white/70 px-5 py-2
							shadow-[0_8px_25px_rgba(0,0,0,0.04)]
							backdrop-blur-xl transition-all duration-300
							hover:-translate-y-1 hover:bg-white
							hover:shadow-[0_15px_35px_rgba(0,0,0,0.08)]"
					>
						<div
							class="flex h-7 w-7 items-center justify-center
								transition-transform duration-300
								group-hover:scale-110"
						>
							<Icon
								icon={tech.icon}
								width="25"
								height="25"
							/>
						</div>

						<span
							class="whitespace-nowrap text-sm font-medium
								text-black/70 transition-colors
								group-hover:text-black"
						>
							{tech.name}
						</span>
					</div>
				{/each}
			</div>
		</div>

		<!-- ========================= -->
		<!-- BACKEND TICKER -->
		<!-- ========================= -->

		<div
			class="ticker-wrapper overflow-hidden border-y border-black/10
				bg-black/[0.035] py-3 backdrop-blur-xl"
		>
			<div class="ticker ticker-right flex w-max items-center">
				{#each backendTicker as tech}
					<div
						class="tech-item group mx-3 flex items-center gap-3
							rounded-full border border-black/8
							bg-white/60 px-5 py-2
							shadow-[0_8px_25px_rgba(0,0,0,0.04)]
							backdrop-blur-xl transition-all duration-300
							hover:-translate-y-1 hover:bg-white
							hover:shadow-[0_15px_35px_rgba(0,0,0,0.08)]"
					>
						<div
							class="flex h-7 w-7 items-center justify-center
								transition-transform duration-300
								group-hover:scale-110"
						>
							<Icon
								icon={tech.icon}
								width="25"
								height="25"
							/>
						</div>

						<span
							class="whitespace-nowrap text-sm font-medium
								text-black/70 transition-colors
								group-hover:text-black"
						>
							{tech.name}
						</span>
					</div>
				{/each}
			</div>
		</div>
	</div>

	<!-- ========================= -->
	<!-- Bottom CTA -->
	<!-- ========================= -->

	<div class="relative z-10 mt-8">
		<a
			href="/tech-stack"
			class="group flex items-center gap-4 rounded-full
				border border-black/10 bg-white/65
				px-10 py-2
				backdrop-blur-xl
				transition-all duration-300
				hover:-translate-y-1
				hover:bg-white
				hover:shadow-[0_15px_40px_rgba(0,0,0,0.1)]"
		>
			<!-- Green availability dot -->

			<span class="relative flex h-2.5 w-2.5">
				<span
					class="absolute inline-flex h-full w-full
						animate-ping rounded-full bg-green-400 opacity-75"
				></span>

				<span
					class="relative inline-flex h-2.5 w-2.5
						rounded-full bg-green-500"
				></span>
			</span>

			<!-- Text -->

			<span
				class="text-[11px] font-semibold uppercase
					tracking-[0.18em] text-black
					transition-all duration-300
					group-hover:tracking-[0.25em]"
			>
				Explore My Stack
			</span>

			<!-- Arrow -->

			<span
				class="flex h-6 w-6 items-center justify-center
					rounded-full bg-black text-white
					transition-all duration-500
					group-hover:rotate-45"
			>
				<svg
					class="h-4 w-4"
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
			</span>
		</a>
	</div>
</section>

<style>
	.ticker {
		animation-duration: 35s;
		animation-timing-function: linear;
		animation-iteration-count: infinite;
	}

	.ticker-left {
		animation-name: move-left;
	}

	.ticker-right {
		animation-name: move-right;
	}

	.ticker-wrapper:hover .ticker {
		animation-play-state: paused;
	}

	@keyframes move-left {
		from {
			transform: translateX(0);
		}

		to {
			transform: translateX(-50%);
		}
	}

	@keyframes move-right {
		from {
			transform: translateX(-50%);
		}

		to {
			transform: translateX(0);
		}
	}
</style>    