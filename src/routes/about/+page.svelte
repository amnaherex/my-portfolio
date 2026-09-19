<script lang="ts">
	const highlights = [
		'Full Stack Development',
		'Interactive Interfaces',
		'Modern Web Applications'
	];
</script>

<section
	id="about"
	class="relative min-h-screen overflow-hidden px-6 py-32 md:px-12 lg:px-20"
>
	<div class="mx-auto max-w-7xl">

		<!-- Section Label -->

		<div class="mb-16">
			<p
				class="text-xs font-medium uppercase tracking-[0.3em] text-black/50"
			>
				About Me
			</p>
		</div>


		<!-- Main Content -->

		<div
			class="grid items-center gap-16 lg:grid-cols-[1fr_0.75fr]"
		>

			<!-- Left Side -->

			<div>

				<h2
					class="max-w-4xl text-6xl font-semibold leading-[0.95] tracking-[-0.05em] text-black md:text-8xl"
				>
					I build digital
					<br />

					<span class="font-serif-display italic">
						experiences
					</span>

					<br />

					with code & curiosity.
				</h2>


				<!-- Description -->

				<div class="mt-12 max-w-2xl space-y-6">

					<p
						class="text-base leading-8 text-black/60 md:text-lg"
					>
						I'm a Full Stack Developer who enjoys turning ideas
						into thoughtful, interactive, and reliable digital
						experiences.
					</p>

					<p
						class="text-base leading-8 text-black/50 md:text-lg"
					>
						I work across the frontend and backend, combining
						clean interfaces with solid application architecture.
						I'm particularly interested in building products
						that feel as good to use as they are to engineer.
					</p>

				</div>


				<!-- Highlights -->

				<div class="mt-12 flex flex-wrap gap-3">

					{#each highlights as highlight}

						<span
							class="rounded-full border border-black/10 bg-white/50 px-4 py-2 text-xs font-medium uppercase tracking-[0.12em] text-black/60 backdrop-blur-xl"
						>
							{highlight}
						</span>

					{/each}

				</div>

			</div>


			<!-- Right Side -->

			<div class="relative flex justify-center">

				<!-- Decorative Glow -->

				<div
					class="absolute left-1/2 top-1/2 h-[350px] w-[350px] -translate-x-1/2 -translate-y-1/2 rounded-full bg-violet-300/20 blur-[120px]"
				></div>


				<!-- Image -->

				<div
					class="relative h-[420px] w-[320px] rotate-[4deg] overflow-hidden rounded-[36px] border border-white/60 bg-white/40 shadow-[0_30px_80px_rgba(0,0,0,0.15)] backdrop-blur-xl transition-transform duration-500 hover:rotate-0"
				>

					<img
						src="/amna.jpg"
						alt="Amna Amjad"
						class="h-full w-full object-cover"
					/>

				</div>


				<!-- Floating Badge -->

				<div
					class="absolute -bottom-6 -left-4 rounded-full border border-white/70 bg-white/70 px-5 py-3 shadow-[0_15px_40px_rgba(0,0,0,0.1)] backdrop-blur-xl md:-left-10"
				>

					<div class="flex items-center gap-2">

						<span class="relative flex h-2.5 w-2.5">

							<span
								class="absolute inline-flex h-full w-full animate-ping rounded-full bg-green-400 opacity-75"
							></span>

							<span
								class="relative inline-flex h-2.5 w-2.5 rounded-full bg-green-500"
							></span>

						</span>

						<span
							class="text-[10px] font-semibold uppercase tracking-[0.18em] text-black/70"
						>
							Available for Work
						</span>

					</div>

				</div>

			</div>

		</div>

	</div>
</section>