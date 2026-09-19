<script lang="ts">
	import { onMount } from 'svelte';

	let identityCard: HTMLDivElement;
	let spotlight: HTMLDivElement;

	let gsap: typeof import('gsap').gsap;

	onMount(async () => {
		const module = await import('gsap');
		gsap = module.gsap;
	});

	function handleCardEnter() {
		if (!gsap) return;

		gsap.to(identityCard, {
			rotate: 0,
			y: -10,
			scale: 1.015,
			duration: 0.7,
			ease: 'power3.out'
		});
	}

	function handleCardLeave() {
		if (!gsap) return;

		gsap.to(identityCard, {
			rotate: 2.5,
			y: 0,
			scale: 1,
			duration: 0.8,
			ease: 'power3.out'
		});

		gsap.to(spotlight, {
			opacity: 0,
			duration: 0.4
		});
	}

	function handleCardMove(event: MouseEvent) {
		if (!gsap) return;

		const rect = identityCard.getBoundingClientRect();

		const x = event.clientX - rect.left;
		const y = event.clientY - rect.top;

		const centerX = rect.width / 2;
		const centerY = rect.height / 2;

		const rotateY = ((x - centerX) / centerX) * 3;
		const rotateX = -((y - centerY) / centerY) * 3;

		gsap.to(identityCard, {
			rotateX,
			rotateY,
			duration: 0.35,
			ease: 'power2.out'
		});

		gsap.to(spotlight, {
			left: x - 130,
			top: y - 130,
			opacity: 1,
			duration: 0.35,
			ease: 'power2.out'
		});
	}
</script>

<section
	id="about"
	class="relative flex min-h-screen items-center justify-center overflow-hidden px-6 py-24 md:px-10"
>
	<!-- ======================================== -->
	<!-- BACKGROUND -->
	<!-- ======================================== -->

	<div class="pointer-events-none absolute inset-0">

		<div
			class="absolute inset-0"
			style="
				background:
					radial-gradient(
						circle at center,
						transparent 45%,
						rgba(0,0,0,.045)
					);
			"
		></div>

		<div
			class="absolute inset-0 opacity-[0.018]"
			style="
				background-image:
					linear-gradient(to right,#000 1px,transparent 1px),
					linear-gradient(to bottom,#000 1px,transparent 1px);
				background-size: 60px 60px;
			"
		></div>

		<div
			class="absolute left-1/2 top-1/2 h-[600px] w-[600px]
				-translate-x-1/2 -translate-y-1/2 rounded-full
				bg-amber-100/20 blur-[130px]"
		></div>

		<div
			class="absolute right-[5%] top-[20%] h-72 w-72
				rounded-full bg-green-300/10 blur-[120px]"
		></div>

		<div
			class="absolute bottom-[10%] left-[5%] h-72 w-72
				rounded-full bg-pink-300/10 blur-[120px]"
		></div>

	</div>


	<!-- ======================================== -->
	<!-- CONTENT -->
	<!-- ======================================== -->

	<div class="relative z-10 w-full max-w-7xl">

		<!-- Label -->

		<div class="mb-8 flex items-center gap-3">

			<span class="h-1.5 w-1.5 rounded-full bg-black"></span>

			<p
				class="text-xs font-medium uppercase tracking-[0.3em] text-black/40"
			>
				A little about me
			</p>

		</div>


		<!-- ======================================== -->
		<!-- MAIN GRID -->
		<!-- ======================================== -->

		<div
			class="grid items-center gap-20 lg:grid-cols-[1fr_390px]"
		>

			<!-- ======================================== -->
			<!-- LEFT -->
			<!-- ======================================== -->

			<div class="max-w-4xl">

				<h2
					class="text-5xl font-semibold leading-[0.98]
						tracking-[-0.055em] text-black
						sm:text-6xl md:text-7xl lg:text-8xl"
				>
					I build,
					<span class="font-serif-display italic">
						lead,
					</span>
					and create.
				</h2>


				<p
	class="mt-8 max-w-2xl text-base leading-8 text-black/50 md:text-lg"
>
	I build for the web by day, lead technology communities
	by passion, and create independently by choice.

	<span class="font-medium p-1 bg-amber-100 rounded-4xl text-black">
		Full Stack Web Developer
	</span>
	at
	<span class="font-medium text-black">
		TARC Solutions
	</span>,

	<span class="font-medium p-1 bg-indigo-50 rounded-4xl text-black">
		Chief Strategist
	</span>
	for
	<span class="font-medium text-black">
		Microsoft Learn Student Ambassadors
	</span>
	society at my university, and a
	<span class="font-medium p-1 bg-pink-100	 rounded-4xl text-black">
		freelancer
	</span>
	turning ideas into thoughtful digital experiences.
</p>


				<!-- About Link -->

				<a
					href="/about"
					class="group mt-10 inline-flex items-center gap-5"
				>

					<span
						class="relative text-xs font-semibold uppercase
							tracking-[0.22em] text-black"
					>
						More about me

						<span
							class="absolute -bottom-2 left-0 h-px w-full
								origin-left scale-x-30 bg-black/30
								transition-transform duration-500
								group-hover:scale-x-100"
						></span>
					</span>

					<span
						class="flex h-9 w-9 items-center justify-center
							rounded-full border border-black/15
							bg-white/50 text-black
							transition-all duration-500
							group-hover:translate-x-2
							group-hover:bg-black
							group-hover:text-white"
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


			<!-- ======================================== -->
			<!-- PREMIUM IDENTITY CARD -->
			<!-- ======================================== -->

			<div class="flex justify-center lg:justify-end">

				<div class="[perspective:1200px]">

					<!-- svelte-ignore a11y_no_static_element_interactions -->

					<div
						bind:this={identityCard}
						onmouseenter={handleCardEnter}
						onmouseleave={handleCardLeave}
						onmousemove={handleCardMove}
						class="relative h-[455px] w-[350px]
							rotate-[2.5deg]
							overflow-hidden
							rounded-[34px]
							border border-black/10
							bg-[#f7f6f2]/90
							p-7
							shadow-[0_35px_90px_rgba(0,0,0,0.14)]
							will-change-transform"
						style="transform-style: preserve-3d;"
					>

						<!-- ================================= -->
						<!-- CURSOR SPOTLIGHT -->
						<!-- ================================= -->

						<div
							bind:this={spotlight}
							class="pointer-events-none absolute
								-left-[130px] -top-[130px]
								h-[260px] w-[260px]
								rounded-full
								bg-white/90 blur-[45px]
								opacity-0"
						></div>


						


						<!-- ================================= -->
						<!-- TOP TECHNICAL MARKS -->
						<!-- ================================= -->

						<div
							class="relative flex items-start justify-between"
						>

							<div class="flex items-center gap-2">

								<span
									class="h-2 w-2 rounded-full bg-green-500"
								></span>

								<span
									class="text-[8px] font-semibold uppercase
										tracking-[0.28em] text-black/40"
								>
									Available
								</span>

							</div>


							<span
								class="font-mono text-[9px]
									tracking-[0.15em] text-black/25"
							>
								AM / 001
							</span>

						</div>


						<!-- ================================= -->
						<!-- HUGE NUMBER -->
						<!-- ================================= -->

						<div class="relative mt-5 h-[105px] overflow-hidden">

							<!-- Large Background Number -->
						
							<span
								class="absolute -left-3 -top-8 text-[150px] font-black
									leading-none tracking-[-0.1em] text-black/[0.035]"
							>
								03
							</span>
						
						
							<!-- Content -->
						
							<div class="relative z-10 flex h-full items-center justify-between">
						
								<!-- Text -->
						
								<div class="pt-5">
						
									<p
										class="text-[9px] font-medium uppercase
											tracking-[0.3em] text-black/35"
									>
										Current chapters
									</p>
						
									<h3
										class="mt-1 text-2xl font-semibold
											tracking-[-0.04em] text-black"
									>
										What I do
									</h3>
						
								</div>
						
						
								<!-- Small Portrait -->
						
								<div
									class="relative mr-1 h-[82px] w-[68px]
										overflow-hidden rounded-2xl	
										"
								>
						
									<img
										src="/amna.jpg"
										alt="Amna"
										class="h-full w-full rounded-[14px] object-cover"
									/>
						
									<!-- Subtle glass overlay -->
						
								
						
								</div>
						
							</div>
						
						</div>


						<!-- ================================= -->
						<!-- DIVIDER -->
						<!-- ================================= -->

						<div class="relative h-px w-full bg-black/10"></div>


						<!-- ================================= -->
						<!-- ROLE 01 -->
						<!-- ================================= -->

						<div
							class="group/role relative flex items-center
								gap-4 border-b border-black/[0.07]
								py-4 transition-all duration-300
								hover:px-2"
						>

							<div
								class="flex h-9 w-9 shrink-0 items-center
									justify-center rounded-full
									bg-black text-[9px] font-bold
									text-white"
							>
								01
							</div>

							<div class="flex-1">

								<p
									class="text-sm font-semibold
										tracking-tight text-black"
								>
									Full Stack Developer
								</p>

								<p
									class="mt-0.5 text-[9px]
										uppercase tracking-[0.12em]
										text-black/35"
								>
									TARC Solutions
								</p>

							</div>

							<span
								class="text-sm text-black/20
									transition-transform duration-300
									group-hover/role:translate-x-1
									group-hover/role:text-black"
							>
								↗
							</span>

						</div>


						<!-- ================================= -->
						<!-- ROLE 02 -->
						<!-- ================================= -->

						<div
							class="group/role relative flex items-center
								gap-4 border-b border-black/[0.07]
								py-4 transition-all duration-300
								hover:px-2"
						>

							<div
								class="flex h-9 w-9 shrink-0 items-center
									justify-center rounded-full
									border border-black/10
									bg-white text-[9px]
									font-bold text-black"
							>
								02
							</div>

							<div class="flex-1">

								<p
									class="text-sm font-semibold
										tracking-tight text-black"
								>
									MLSA Executive
								</p>

								<p
									class="mt-0.5 text-[9px]
										uppercase tracking-[0.12em]
										text-black/35"
								>
									Technology Community
								</p>

							</div>

							<span
								class="text-sm text-black/20
									transition-transform duration-300
									group-hover/role:translate-x-1
									group-hover/role:text-black"
							>
								↗
							</span>

						</div>


						<!-- ================================= -->
						<!-- ROLE 03 -->
						<!-- ================================= -->

						<div
							class="group/role relative flex items-center
								gap-4 py-4 transition-all duration-300
								hover:px-2"
						>

							<div
								class="flex h-9 w-9 shrink-0 items-center
									justify-center rounded-full
									border border-black/10
									bg-white text-[9px]
									font-bold text-black"
							>
								03
							</div>

							<div class="flex-1">

								<p
									class="text-sm font-semibold
										tracking-tight text-black"
								>
									Freelancer
								</p>

								<p
									class="mt-0.5 text-[9px]
										uppercase tracking-[0.12em]
										text-black/35"
								>
									Independent Projects
								</p>

							</div>

							<span
								class="text-sm text-black/20
									transition-transform duration-300
									group-hover/role:translate-x-1
									group-hover/role:text-black"
							>
								↗
							</span>

						</div>


						<!-- ================================= -->
						<!-- FOOTER -->
						<!-- ================================= -->

						<div
							class="absolute bottom-7 left-7 right-7
								flex items-end justify-between"
						>

							<div>

								<p
									class="text-[8px] font-medium
										uppercase tracking-[0.25em]
										text-black/25"
								>
									Based in
								</p>

								<p
									class="mt-1 text-[10px]
										font-semibold text-black/60"
								>
									Lahore, Pakistan
								</p>

							</div>


							<div class="text-right">

								<p
									class="font-mono text-[9px]
										text-black/25"
								>
									2026
								</p>

								<div
									class="mt-1 flex items-center
										gap-1"
								>

									<span
										class="h-1 w-1 rounded-full
											bg-black/30"
									></span>

									<span
										class="h-1 w-1 rounded-full
											bg-black/15"
									></span>

									<span
										class="h-1 w-1 rounded-full
											bg-black/10"
									></span>

								</div>

							</div>

						</div>


						<!-- ================================= -->
						<!-- GRAIN -->
						<!-- ================================= -->

						<div
							class="pointer-events-none absolute inset-0
								opacity-[0.025]"
							style="
								background-image:
									radial-gradient(
										#000 0.4px,
										transparent 0.4px
									);
								background-size: 4px 4px;
							"
						></div>

					</div>

				</div>

			</div>

		</div>


		<!-- ======================================== -->
		<!-- BOTTOM ROLE STRIP -->
		<!-- ======================================== -->

		<div
			class="mt-24 flex flex-wrap items-center
				justify-center gap-x-8 gap-y-4
				border-t border-black/10 pt-6"
		>

			<span
				class="text-[10px] font-medium uppercase
					tracking-[0.2em] text-black/35 md:text-xs"
			>
				Full Stack Developer
			</span>

			<span class="h-1 w-1 rounded-full bg-black/20"></span>

			<span
				class="text-[10px] font-medium uppercase
					tracking-[0.2em] text-black/35 md:text-xs"
			>
				MLSA Executive
			</span>

			<span class="h-1 w-1 rounded-full bg-black/20"></span>

			<span
				class="text-[10px] font-medium uppercase
					tracking-[0.2em] text-black/35 md:text-xs"
			>
				Freelancer
			</span>

		</div>

	</div>

</section>