<script lang="ts">
	import { onMount } from 'svelte';

	let gsap: typeof import('gsap').gsap;

	let card: HTMLDivElement;

	onMount(async () => {
		const module = await import('gsap');
		gsap = module.gsap;

		// Card entrance animation
		gsap.from(card, {
			y: 80,
			opacity: 0,
			rotation: -20,
			duration: 1.2,
			ease: 'power3.out'
		});

		// Floating shapes
		const shapes = gsap.utils.toArray<HTMLElement>('.floating-shape');

		shapes.forEach((shape, index) => {
			// Entrance animation
			gsap.from(shape, {
				y: -80,
				opacity: 0,
				scale: 0,
				rotation: gsap.utils.random(-180, 180),
				duration: 1,
				delay: index * 0.15,
				ease: 'back.out(1.7)'
			});

			// Continuous floating animation
			gsap.to(shape, {
				y: gsap.utils.random(-15, -35),
				x: gsap.utils.random(-8, 8),
				rotation: gsap.utils.random(-15, 15),
				duration: gsap.utils.random(2.5, 4),
				repeat: -1,
				yoyo: true,
				ease: 'sine.inOut'
			});
		});
	});

	function handleMouseMove(event: MouseEvent) {
		if (!gsap || !card) return;

		const rect = card.getBoundingClientRect();

		const x = event.clientX - rect.left;
		const y = event.clientY - rect.top;

		const centerX = rect.width / 2;
		const centerY = rect.height / 2;

		const rotateY = ((x - centerX) / centerX) * 15;
		const rotateX = -((y - centerY) / centerY) * 15;

		gsap.to(card, {
			rotateX,
			rotateY,
			duration: 0.25,
			ease: 'power3.out'
		});
	}

	function handleMouseLeave() {
		if (!gsap || !card) return;

		gsap.to(card, {
			rotateX: 0,
			rotateY: 0,
			duration: 0.8,
			ease: 'power3.out'
		});
	}
</script>

<section
	id="home"
	class="relative flex min-h-screen items-center justify-center overflow-hidden "
>
	<!-- ============================================ -->
	<!-- Decorative Floating Shapes -->
	<!-- ============================================ -->
	
	<img
		src="/star-black.png"
		alt=""
		aria-hidden="true"
		class="floating-shape absolute right-[8%] top-[16%] z-20 w-16 drop-shadow-[0_25px_35px_rgba(0,0,0,0.15)] sm:right-[12%] sm:top-[18%] sm:w-20 md:right-[20%] md:top-[20%] md:w-36"
	/>
	
	<img
		src="/shape2.png"
		alt=""
		aria-hidden="true"
		class="floating-shape absolute left-[5%] top-[20%] z-20 w-16 drop-shadow-[0_25px_35px_rgba(0,0,0,0.15)] sm:left-[8%] sm:w-20 md:left-[12%] md:w-40"
	/>
	
	<img
		src="/shape3.png"
		alt=""
		aria-hidden="true"
		class="floating-shape absolute bottom-[8%] left-[6%] z-20 w-16 drop-shadow-[0_25px_35px_rgba(0,0,0,0.15)] sm:left-[12%] sm:w-20 md:bottom-[10%] md:left-[18%] md:w-44"
	/>
	
	<img
		src="/shape4.png"
		alt=""
		aria-hidden="true"
		class="floating-shape absolute bottom-[8%] right-[6%] z-20 w-16 drop-shadow-[0_25px_35px_rgba(0,0,0,0.15)] sm:right-[12%] sm:w-20 md:bottom-[10%] md:right-[18%] md:w-40"
	/>
	
	<img
		src="/shape5.png"
		alt=""
		aria-hidden="true"
		class="floating-shape absolute left-[2%] top-[45%] z-20 w-16 drop-shadow-[0_25px_35px_rgba(0,0,0,0.15)] sm:left-[6%] sm:w-20 md:left-[10%] md:top-[46%] md:w-40"
	/>
	
	<img
		src="/shape6.png"
		alt=""
		aria-hidden="true"
		class="floating-shape absolute right-[2%] top-[43%] z-20 w-16 drop-shadow-[0_25px_35px_rgba(0,0,0,0.15)] sm:right-[6%] sm:w-20 md:right-[10%] md:top-[44%] md:w-40"
	/>
	
	<!-- ============================================ -->
	<!-- Background Typography -->
	<!-- ============================================ -->
	
	<h1
		class="pointer-events-none absolute inset-x-0 top-28 z-0 flex flex-col text-center font-black uppercase leading-[0.82] tracking-[-0.04em] text-black/[0.055] select-none md:top-32"
	>
		<span
			class="text-[4.8rem] xs:text-[5.5rem] sm:text-[7.5rem] md:text-[13rem] lg:text-[14rem]"
		>
			Software
		</span>
	
		<span
			class="text-[4.35rem] xs:text-[5rem] sm:text-[7rem] md:text-[12rem] lg:text-[13rem]"
		>
			Developer
		</span>
	</h1>
	
	<!-- ============================================ -->
	<!-- Hero Content -->
	<!-- ============================================ -->
	
	<div
		class="relative z-30 flex flex-col items-center px-6 text-center"
	>
		<!-- Greeting -->
	
		<p
			class="text-3xl font-semibold tracking-tight text-black sm:text-4xl md:text-5xl"
		>
			Hi, I'm
	
			<span
				class="font-serif-display ml-1 text-4xl italic sm:text-5xl md:text-6xl"
			>
				Amna!
			</span>
		</p>
	
		<!-- Subtitle -->
	
		<p
			class="text-[10px] font-medium uppercase tracking-[0.22em] text-gray-500 sm:text-xs sm:tracking-[0.3em] md:text-sm"
		>
			Full Stack Web Developer
		</p>
	
		<!-- ============================================ -->
		<!-- Portrait -->
		<!-- ============================================ -->
	
		<div class="relative mt-6 [perspective:1200px] md:mt-8">
			<!-- Portrait Glow -->
	
			<div
				class="pointer-events-none absolute left-1/2 top-1/2 -z-10 h-[260px] w-[260px] -translate-x-1/2 -translate-y-1/2 rounded-full bg-violet-300/20 blur-[90px] sm:h-[320px] sm:w-[320px] sm:blur-[110px] md:h-[420px] md:w-[420px] md:blur-[130px]"
			></div>
	
			<!-- Glass Frame -->
	
			<!-- svelte-ignore a11y_no_static_element_interactions -->
	
			<div
				bind:this={card}
				onmousemove={handleMouseMove}
				onmouseleave={handleMouseLeave}
				class="h-[270px] w-[270px] overflow-hidden rounded-[32px] border border-white/50 shadow-[0_30px_60px_rgba(0,0,0,0.18)] will-change-transform sm:h-[320px] sm:w-[300px] md:h-[400px] md:w-[320px]"
				style="transform-style: preserve-3d;"
			>
				<img
					src="/amna.jpg"
					alt="Amna Amjad - Full Stack Web Developer"
					class="h-full w-full object-cover"
					style="transform: translateZ(40px);"
					width="320"
					height="400"
					loading="eager"
					fetchpriority="high"
				/>
			</div>
		</div>
	
		<!-- ============================================ -->
		<!-- CTA -->
		<!-- ============================================ -->
	
		<a
			href="#contact"
			aria-label="Let's build a project together"
			class="group flex items-center gap-2 rounded-full border border-white/60 bg-white/35 px-2 py-2 shadow-[0_8px_30px_rgba(0,0,0,0.08)] backdrop-blur-xl ring-1 ring-white/30 transition-all mt-3.5 duration-500 hover:-translate-y-0.5 hover:bg-white/50 hover:shadow-[0_15px_40px_rgba(0,0,0,0.12)] focus:outline-none focus:ring-2 focus:ring-black/30 focus:ring-offset-2"
		>
			<!-- Green Status -->
	
			<span class="relative ml-1.5 flex h-2.5 w-2.5">
				<span
					class="absolute inline-flex h-full w-full animate-ping rounded-full bg-green-400 opacity-70"
				></span>
	
				<span
					class="relative inline-flex h-2.5 w-2.5 rounded-full bg-green-500 shadow-[0_0_8px_rgba(34,197,94,0.6)]"
				></span>
			</span>
	
			<!-- CTA Text -->
	
			<span
				class="px-1 text-[11px] font-semibold tracking-[0.16em] text-black transition-all duration-300 group-hover:tracking-[0.22em]"
			>
				LET'S BUILD
			</span>
	
			<!-- Arrow Circle -->
	
			<span
				class="flex h-5 w-5 items-center justify-center rounded-full bg-black text-white shadow-md transition-all duration-500 group-hover:rotate-[-45deg] group-hover:scale-105"
				aria-hidden="true"
			>
				<svg
					class="h-3.5 w-3.5"
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