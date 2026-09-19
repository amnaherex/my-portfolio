<script lang="ts">
	import { onMount } from 'svelte';
	import  Icon from '@iconify/svelte';

	let gsap: typeof import('gsap').gsap;

	let section: HTMLElement;
	let card: HTMLDivElement;

	// Frontend logos
	let reactLogo: HTMLDivElement;
	let nextLogo: HTMLDivElement;
	let tailwindLogo: HTMLDivElement;
	let svelteLogo: HTMLDivElement;
	let zodLogo: HTMLDivElement;
	let zustandLogo: HTMLDivElement;
	let framerLogo: HTMLDivElement;
	let gsapLogo: HTMLDivElement;

	// Backend logos
	let nodeLogo: HTMLDivElement;
	let nestLogo: HTMLDivElement;
	let postgresLogo: HTMLDivElement;
	let prismaLogo: HTMLDivElement;
	let supabaseLogo: HTMLDivElement;
	let dockerLogo: HTMLDivElement;
	let apiLogo: HTMLDivElement;
	let typescriptLogo: HTMLDivElement;

	onMount(async () => {
		const gsapModule = await import('gsap');
		const scrollTriggerModule = await import('gsap/ScrollTrigger');

		gsap = gsapModule.gsap;

		const ScrollTrigger = scrollTriggerModule.ScrollTrigger;

		gsap.registerPlugin(ScrollTrigger);

		/* ============================================
		   FRONTEND INITIAL POSITIONS
		============================================ */

		gsap.set(reactLogo, {
			x: -180,
			y: -30,
			rotation: -25,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(nextLogo, {
			x: 180,
			y: -30,
			rotation: 25,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(tailwindLogo, {
			x: -80,
			y: -130,
			rotation: -20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(svelteLogo, {
			x: 80,
			y: -130,
			rotation: 20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(zodLogo, {
			x: -160,
			y: 100,
			rotation: -20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(zustandLogo, {
			x: 160,
			y: 100,
			rotation: 20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(framerLogo, {
			x: -70,
			y: 130,
			rotation: -18,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(gsapLogo, {
			x: 70,
			y: 130,
			rotation: 18,
			scale: 0.7,
			opacity: 0
		});

		/* ============================================
		   BACKEND INITIAL POSITIONS
		============================================ */

		gsap.set(nodeLogo, {
			x: -180,
			y: -30,
			rotation: -25,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(nestLogo, {
			x: 180,
			y: -30,
			rotation: 25,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(postgresLogo, {
			x: -80,
			y: -130,
			rotation: -20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(prismaLogo, {
			x: 80,
			y: -130,
			rotation: 20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(supabaseLogo, {
			x: -160,
			y: 100,
			rotation: -20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(dockerLogo, {
			x: 160,
			y: 100,
			rotation: 20,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(apiLogo, {
			x: -70,
			y: 130,
			rotation: -18,
			scale: 0.7,
			opacity: 0
		});

		gsap.set(typescriptLogo, {
			x: 70,
			y: 130,
			rotation: 18,
			scale: 0.7,
			opacity: 0
		});

		/* ============================================
		   CARD FLIP
		============================================ */

		gsap.fromTo(
			card,
			{
				rotateX: 0
			},
			{
				rotateX: 180,
				ease: 'none',
				scrollTrigger: {
					trigger: section,
					start: 'top top',
					end: '+=100%',
					scrub: 1,
					pin: true
				}
			}
		);
	});

	/* ============================================
	   CARD HOVER ENTER
	============================================ */

	function handleCardEnter() {
	if (!gsap) return;

	// Kill any previous logo animations
	gsap.killTweensOf([
		reactLogo,
		nextLogo,
		tailwindLogo,
		svelteLogo,
		zodLogo,
		zustandLogo,
		framerLogo,
		gsapLogo,
		nodeLogo,
		nestLogo,
		postgresLogo,
		prismaLogo,
		supabaseLogo,
		dockerLogo,
		apiLogo,
		typescriptLogo
	]);

	// Always reset logos before entering
	gsap.set(reactLogo, {
		x: -180,
		y: -30,
		rotation: -25,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(nextLogo, {
		x: 180,
		y: -30,
		rotation: 25,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(tailwindLogo, {
		x: -80,
		y: -130,
		rotation: -20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(svelteLogo, {
		x: 80,
		y: -130,
		rotation: 20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(zodLogo, {
		x: -160,
		y: 100,
		rotation: -20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(zustandLogo, {
		x: 160,
		y: 100,
		rotation: 20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(framerLogo, {
		x: -70,
		y: 130,
		rotation: -18,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(gsapLogo, {
		x: 70,
		y: 130,
		rotation: 18,
		scale: 0.7,
		opacity: 0
	});

	// Backend
	gsap.set(nodeLogo, {
		x: -180,
		y: -30,
		rotation: -25,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(nestLogo, {
		x: 180,
		y: -30,
		rotation: 25,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(postgresLogo, {
		x: -80,
		y: -130,
		rotation: -20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(prismaLogo, {
		x: 80,
		y: -130,
		rotation: 20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(supabaseLogo, {
		x: -160,
		y: 100,
		rotation: -20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(dockerLogo, {
		x: 160,
		y: 100,
		rotation: 20,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(apiLogo, {
		x: -70,
		y: 130,
		rotation: -18,
		scale: 0.7,
		opacity: 0
	});

	gsap.set(typescriptLogo, {
		x: 70,
		y: 130,
		rotation: 18,
		scale: 0.7,
		opacity: 0
	});

	const tl = gsap.timeline();

	// Tumhara existing logo entrance animation yahan continue hoga

		/* --------------------------------------------
		   FRONTEND LOGOS
		-------------------------------------------- */

		tl.to(
			reactLogo,
			{
				x: 0,
				y: 0,
				rotation: -8,
				scale: 1,
				opacity: 1,
				duration: 0.7,
				ease: 'back.out(1.7)'
			},
			0
		)
			.to(
				nextLogo,
				{
					x: 0,
					y: 0,
					rotation: 8,
					scale: 1,
					opacity: 1,
					duration: 0.7,
					ease: 'back.out(1.7)'
				},
				0.08
			)
			.to(
				tailwindLogo,
				{
					x: 0,
					y: 0,
					rotation: -6,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.14
			)
			.to(
				svelteLogo,
				{
					x: 0,
					y: 0,
					rotation: 6,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.18
			)
			.to(
				zodLogo,
				{
					x: 0,
					y: 0,
					rotation: -7,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.22
			)
			.to(
				zustandLogo,
				{
					x: 0,
					y: 0,
					rotation: 7,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.26
			)
			.to(
				framerLogo,
				{
					x: 0,
					y: 0,
					rotation: -5,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.3
			)
			.to(
				gsapLogo,
				{
					x: 0,
					y: 0,
					rotation: 5,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.34
			);

		/* --------------------------------------------
		   BACKEND LOGOS
		-------------------------------------------- */

		tl.to(
			nodeLogo,
			{
				x: 0,
				y: 0,
				rotation: -8,
				scale: 1,
				opacity: 1,
				duration: 0.7,
				ease: 'back.out(1.7)'
			},
			0
		)
			.to(
				nestLogo,
				{
					x: 0,
					y: 0,
					rotation: 8,
					scale: 1,
					opacity: 1,
					duration: 0.7,
					ease: 'back.out(1.7)'
				},
				0.08
			)
			.to(
				postgresLogo,
				{
					x: 0,
					y: 0,
					rotation: -6,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.14
			)
			.to(
				prismaLogo,
				{
					x: 0,
					y: 0,
					rotation: 6,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.18
			)
			.to(
				supabaseLogo,
				{
					x: 0,
					y: 0,
					rotation: -7,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.22
			)
			.to(
				dockerLogo,
				{
					x: 0,
					y: 0,
					rotation: 7,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.26
			)
			.to(
				apiLogo,
				{
					x: 0,
					y: 0,
					rotation: -5,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.3
			)
			.to(
				typescriptLogo,
				{
					x: 0,
					y: 0,
					rotation: 5,
					scale: 1,
					opacity: 1,
					duration: 0.65,
					ease: 'back.out(1.7)'
				},
				0.34
			);
	}

	/* ============================================
	   CARD HOVER LEAVE
	============================================ */

	function handleCardLeave() {
	if (!gsap) return;

	gsap.killTweensOf([
		reactLogo,
		nextLogo,
		tailwindLogo,
		svelteLogo,
		zodLogo,
		zustandLogo,
		framerLogo,
		gsapLogo,
		nodeLogo,
		nestLogo,
		postgresLogo,
		prismaLogo,
		supabaseLogo,
		dockerLogo,
		apiLogo,
		typescriptLogo
	]);

	const tl = gsap.timeline();

		/* --------------------------------------------
		   FRONTEND LOGOS EXIT
		-------------------------------------------- */

		tl.to(
			reactLogo,
			{
				x: -180,
				y: -30,
				rotation: -25,
				scale: 0.7,
				opacity: 0,
				duration: 0.55,
				ease: 'power2.in'
			},
			0
		)
			.to(
				nextLogo,
				{
					x: 180,
					y: -30,
					rotation: 25,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.04
			)
			.to(
				tailwindLogo,
				{
					x: -80,
					y: -130,
					rotation: -20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.08
			)
			.to(
				svelteLogo,
				{
					x: 80,
					y: -130,
					rotation: 20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.12
			)
			.to(
				zodLogo,
				{
					x: -160,
					y: 100,
					rotation: -20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.16
			)
			.to(
				zustandLogo,
				{
					x: 160,
					y: 100,
					rotation: 20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.2
			)
			.to(
				framerLogo,
				{
					x: -70,
					y: 130,
					rotation: -18,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.24
			)
			.to(
				gsapLogo,
				{
					x: 70,
					y: 130,
					rotation: 18,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.28
			);

		/* --------------------------------------------
		   BACKEND LOGOS EXIT
		-------------------------------------------- */

		tl.to(
			nodeLogo,
			{
				x: -180,
				y: -30,
				rotation: -25,
				scale: 0.7,
				opacity: 0,
				duration: 0.55,
				ease: 'power2.in'
			},
			0
		)
			.to(
				nestLogo,
				{
					x: 180,
					y: -30,
					rotation: 25,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.04
			)
			.to(
				postgresLogo,
				{
					x: -80,
					y: -130,
					rotation: -20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.08
			)
			.to(
				prismaLogo,
				{
					x: 80,
					y: -130,
					rotation: 20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.12
			)
			.to(
				supabaseLogo,
				{
					x: -160,
					y: 100,
					rotation: -20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.16
			)
			.to(
				dockerLogo,
				{
					x: 160,
					y: 100,
					rotation: 20,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.2
			)
			.to(
				apiLogo,
				{
					x: -70,
					y: 130,
					rotation: -18,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.24
			)
			.to(
				typescriptLogo,
				{
					x: 70,
					y: 130,
					rotation: 18,
					scale: 0.7,
					opacity: 0,
					duration: 0.55,
					ease: 'power2.in'
				},
				0.28
			);
	}
</script>

<section
	bind:this={section}
	class="relative flex min-h-screen flex-col items-center justify-center [perspective:1200px]"
>
	<!-- Section Label -->

	<p
		class="text-[10px] font-medium uppercase tracking-[0.22em] text-black sm:text-xs sm:tracking-[0.3em] md:text-[20px]"
	>
		What I Do
	</p>

	<!-- Background Grid -->

	<div
		class="pointer-events-none absolute inset-0 opacity-[0.025]"
		style="
			background-image:
				linear-gradient(to right,#000 1px,transparent 1px),
				linear-gradient(to bottom,#000 1px,transparent 1px);
			background-size: 60px 60px;
		"
	></div>

	<!-- Card Wrapper -->

	<div
		class="relative mt-5 h-[500px] w-[1000px]"
		style="transform-style: preserve-3d;"
	>
		<!-- Animated Card -->

		<div
			bind:this={card}
			onmouseenter={handleCardEnter}
			onmouseleave={handleCardLeave}
			class="relative h-full w-full rounded-4xl shadow-2xl will-change-transform"
			style="transform-style: preserve-3d;"
		>
			<!-- ========================================
			     FRONT FACE
			========================================= -->

			<div
				class="absolute inset-0 flex flex-col items-center rounded-4xl bg-white/40 p-10 backdrop-blur-xl"
				style="
					backface-visibility: hidden;
					transform: rotateX(0deg);
				"
			>
				<!-- Corner Borders -->

				<div class="pointer-events-none absolute inset-5">
					<div
						class="absolute left-0 top-0 h-8 w-8 border-l border-t border-black/15"
					></div>

					<div
						class="absolute right-0 top-0 h-8 w-8 border-r border-t border-black/15"
					></div>

					<div
						class="absolute bottom-0 left-0 h-8 w-8 border-b border-l border-black/15"
					></div>

					<div
						class="absolute bottom-0 right-0 h-8 w-8 border-b border-r border-black/15"
					></div>
				</div>

				<!-- Browser Header -->

				<div class="flex w-full items-center">
					<div class="flex items-start gap-2">
						<span class="h-3.5 w-3.5 rounded-full bg-red-400"></span>

						<span class="h-3.5 w-3.5 rounded-full bg-yellow-400"></span>

						<span class="h-3.5 w-3.5 rounded-full bg-green-500"></span>
					</div>
				</div>

				<!-- Frontend Logos -->

				<div
					bind:this={reactLogo}
					class="absolute left-20 top-[185px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:react" class="text-3xl" />
				</div>

				<div
					bind:this={nextLogo}
					class="absolute right-20 top-[185px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:nextjs-icon" class="text-3xl" />
				</div>

				<div
					bind:this={tailwindLogo}
					class="absolute left-[230px] top-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:tailwindcss-icon" class="text-3xl" />
				</div>

				<div
					bind:this={svelteLogo}
					class="absolute right-[230px] top-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:svelte-icon" class="text-3xl" />
				</div>

				<div
					bind:this={zodLogo}
					class="absolute bottom-24 left-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<span class="text-sm font-black text-black">Zod</span>
				</div>

				<div
					bind:this={zustandLogo}
					class="absolute bottom-24 right-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<span class="text-xs font-black text-black">Z</span>
				</div>

				<div
					bind:this={framerLogo}
					class="absolute bottom-16 left-[230px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:framer" class="text-3xl" />
				</div>

				<div
					bind:this={gsapLogo}
					class="absolute bottom-16 right-[230px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<span class="text-xs font-black text-black">GSAP</span>
				</div>

				<!-- Front Content -->

				<h2
					class="relative z-10 mt-10 text-7xl font-semibold tracking-tight text-black"
				>
					Frontend
				</h2>

				<p
					class="relative z-10 mt-10 max-w-3xl text-center text-[18px] leading-8 text-gray-700"
				>
					I turn creative ideas into modern web experiences,
					designing interfaces that feel fast, intuitive, and
					beautiful. I build responsive experiences with modern
					frontend technologies and thoughtful interaction.
				</p>
				<div
	class="absolute bottom-7 left-1/2 -translate-x-1/2  px-4 py-2 opacity-20 transition-all duration-500 group-hover:opacity-0"
>
	<span
		class="text-[10px] font-medium uppercase tracking-[0.2em] text-black/50"
	>
		Hover to see tech stack
	</span>
</div>
			</div>

			<!-- ========================================
			     BACK FACE
			========================================= -->

			<div
				class="absolute inset-0 flex flex-col items-center rounded-4xl bg-white/40 p-10 backdrop-blur-xl"
				style="
					backface-visibility: hidden;
					transform: rotateX(180deg);
				"
			>
				<!-- Corner Borders -->

				<div class="pointer-events-none absolute inset-5">
					<div
						class="absolute left-0 top-0 h-8 w-8 border-l border-t border-black/15"
					></div>

					<div
						class="absolute right-0 top-0 h-8 w-8 border-r border-t border-black/15"
					></div>

					<div
						class="absolute bottom-0 left-0 h-8 w-8 border-b border-l border-black/15"
					></div>

					<div
						class="absolute bottom-0 right-0 h-8 w-8 border-b border-r border-black/15"
					></div>
				</div>

				<!-- Browser Header -->

				<div class="flex w-full items-center">
					<div class="flex items-start gap-2">
						<span class="h-3.5 w-3.5 rounded-full bg-red-400"></span>

						<span class="h-3.5 w-3.5 rounded-full bg-yellow-400"></span>

						<span class="h-3.5 w-3.5 rounded-full bg-green-500"></span>
					</div>
				</div>

				<!-- Backend Logos -->

				<div
					bind:this={nodeLogo}
					class="absolute left-20 top-[185px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:nodejs-icon" class="text-3xl" />
				</div>

				<div
					bind:this={nestLogo}
					class="absolute right-20 top-[185px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:nestjs" class="text-3xl" />
				</div>

				<div
					bind:this={postgresLogo}
					class="absolute left-[230px] top-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:postgresql" class="text-3xl" />
				</div>

				<div
					bind:this={prismaLogo}
					class="absolute right-[230px] top-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:prisma" class="text-3xl" />
				</div>

				<div
					bind:this={supabaseLogo}
					class="absolute bottom-24 left-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:supabase-icon" class="text-3xl" />
				</div>

				<div
					bind:this={dockerLogo}
					class="absolute bottom-24 right-20 z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:docker-icon" class="text-3xl" />
				</div>

				<div
					bind:this={apiLogo}
					class="absolute bottom-16 left-[230px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<span class="text-xs font-black uppercase tracking-tight text-black">
						API
					</span>
				</div>

				<div
					bind:this={typescriptLogo}
					class="absolute bottom-16 right-[230px] z-20 flex h-14 w-14 items-center justify-center rounded-2xl border border-white/70 bg-white/70 shadow-lg backdrop-blur-xl"
				>
					<Icon icon="logos:typescript-icon" class="text-3xl" />
				</div>

				<!-- Backend Content -->

				<h2
					class="relative z-10 mt-10 text-7xl font-semibold tracking-tight text-black"
				>
					Backend
				</h2>

				<p
					class="relative z-10 mt-10 max-w-3xl text-center text-[18px] leading-8 text-gray-700"
				>
					I build robust backend systems that power reliable
					applications. I work with APIs, databases, authentication,
					server-side logic, and scalable architectures to create
					smooth experiences from the inside out.
				</p>
				<div
	class="absolute bottom-7 left-1/2 -translate-x-1/2  px-4 py-2 opacity-20 transition-all duration-500 group-hover:opacity-0"
>
	<span
		class="text-[10px] font-medium uppercase tracking-[0.2em] text-black/50"
	>
		Hover to see tech stack
	</span>
</div>
			</div>
		</div>
	</div>
</section>