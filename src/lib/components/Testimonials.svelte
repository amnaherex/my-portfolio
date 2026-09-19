<script lang="ts">
	const testimonials = [
		{
			name: 'Sarah Khan',
			role: 'Product Designer',
			initials: 'SK',
			text: 'Amna brings a strong mix of technical thinking and attention to detail.'
		},
		{
			name: 'Hamza Ali',
			role: 'Software Engineer',
			initials: 'HA',
			text: 'She is thoughtful with her implementation and genuinely cares about the final experience.'
		},
		{
			name: 'Ayesha Malik',
			role: 'Project Lead',
			initials: 'AM',
			text: 'Working with Amna feels easy because she understands both design and development.'
		},
		{
			name: 'Usman Raza',
			role: 'Frontend Developer',
			initials: 'UR',
			text: 'Her attention to interaction and small details makes her work stand out.'
		},
		{
			name: 'Maha Ahmed',
			role: 'Community Lead',
			initials: 'MA',
			text: 'Amna consistently brings energy, curiosity, and ownership to everything she builds.'
		},
		{
			name: 'Ali Hassan',
			role: 'Full Stack Developer',
			initials: 'AH',
			text: 'A developer who thinks beyond just making things work.'
		}
	];

	const firstRow = [...testimonials, ...testimonials];
	const secondRow = [...testimonials.slice().reverse(), ...testimonials.slice().reverse()];
</script>

<section
	class="relative overflow-hidden py-10"
>
	<!-- ======================================== -->
	<!-- Section Header -->
	<!-- ======================================== -->

	<div class="relative z-10 mx-auto mb-20 max-w-7xl px-6 md:px-10">

		<p
			class="mb-5 text-xs font-medium uppercase
				tracking-[0.3em] text-black/40"
		>
			Kind words
		</p>

		<div
			class="flex flex-col justify-between gap-3 md:flex-row md:items-end"
		>

			<h2
				class="max-w-3xl text-5xl font-semibold
					leading-[0.95] tracking-[-0.05em]
					text-black md:text-7xl"
			>
				What people
				<span class="font-serif-display italic">
					say.
				</span>
			</h2>

			<p
				class="max-w-sm text-sm leading-7 text-black/45"
			>
				A few words from people I've had the pleasure
				of working, building, and creating with.
			</p>

		</div>

	</div>


	<!-- ======================================== -->
	<!-- Fade Masks -->
	<!-- ======================================== -->

	<div
		class="pointer-events-none absolute left-0 top-0 z-20
			h-full w-24 bg-gradient-to-r
			from-white to-transparent md:w-40"
	></div>

	<div
		class="pointer-events-none absolute right-0 top-0 z-20
			h-full w-24 bg-gradient-to-l
			from-white to-transparent md:w-40"
	></div>


	<!-- ======================================== -->
	<!-- ROW ONE -->
	<!-- ======================================== -->

	<div
		class="testimonial-row group mb-3    flex w-max
			gap-5"
	>
		{#each firstRow as testimonial}
			<article
				class="w-[400px] shrink-0 rounded-[26px]
					border border-black/[0.07]
					bg-white/55 p-6
					shadow-[0_15px_45px_rgba(0,0,0,0.05)]
					backdrop-blur-xl
					transition-all duration-300
					hover:-translate-y-1
					hover:bg-white
					hover:shadow-[0_20px_50px_rgba(0,0,0,0.09)]"
			>

				<!-- Quote -->

				<div class="mb-3 flex items-start justify-between">

					<span
						class="font-serif-display text-4xl
							leading-none text-black/15"
					>
						“
					</span>

					<span
						class="text-[9px] font-medium uppercase
							tracking-[0.2em] text-black/20"
					>
						01 / 06
					</span>

				</div>


				<!-- Testimonial -->

				<p
					class="min-h-[50px] text-sm leading-7
						text-black/65"
				>
					{testimonial.text}
				</p>


				<!-- Person -->

				<div
					class="mt-7 flex items-center gap-3
						border-t border-black/[0.07]
						pt-5"
				>

					<div
						class="flex h-9 w-9 items-center
							justify-center rounded-full
							bg-black text-[9px] font-semibold
							text-white"
					>
						{testimonial.initials}
					</div>

					<div>

						<p
							class="text-xs font-semibold
								text-black"
						>
							{testimonial.name}
						</p>

						<p
							class="mt-0.5 text-[9px]
								uppercase tracking-[0.12em]
								text-black/35"
						>
							{testimonial.role}
						</p>

					</div>

				</div>

			</article>
		{/each}
	</div>


	<!-- ======================================== -->
	<!-- ROW TWO -->
	<!-- ======================================== -->

	<div
		class="testimonial-row-reverse group flex w-max
			gap-5"
	>
		{#each secondRow as testimonial}
			<article
				class="w-[400px] shrink-0 rounded-[26px]
					border border-black/[0.07]
					bg-white/45 p-6
					shadow-[0_15px_45px_rgba(0,0,0,0.04)]
					backdrop-blur-xl
					transition-all duration-300
					hover:-translate-y-1
					hover:bg-white
					hover:shadow-[0_20px_50px_rgba(0,0,0,0.09)]"
			>

				<div class="mb-3 flex items-start justify-between">

					<span
						class="font-serif-display text-4xl
							leading-none text-black/15"
					>
						“
					</span>

					<span
						class="text-[9px] font-medium uppercase
							tracking-[0.2em] text-black/20"
					>
						02 / 06
					</span> 

				</div>


				<p
					class="min-h-[50px] text-sm leading-7
						text-black/65"
				>
					{testimonial.text}
				</p>


				<div
					class="mt-7 flex items-center gap-3
						border-t border-black/[0.07]
						pt-5"
				>

					<div
						class="flex h-9 w-9 items-center
							justify-center rounded-full
							border border-black/10
							bg-white text-[9px]
							font-semibold text-black"
					>
						{testimonial.initials}
					</div>

					<div>

						<p
							class="text-xs font-semibold
								text-black"
						>
							{testimonial.name}
						</p>

						<p
							class="mt-0.5 text-[9px]
								uppercase tracking-[0.12em]
								text-black/35"
						>
							{testimonial.role}
						</p>

					</div>

				</div>

			</article>
		{/each}
	</div>


	<!-- ======================================== -->
	<!-- Bottom Label -->
	<!-- ======================================== -->

	<div
		class="relative z-10 mt-16 flex justify-center"
	>

		<div
			class="flex items-center gap-3 rounded-full
				border border-black/10 bg-white/50
				px-5 py-2.5 backdrop-blur-xl"
		>

			<span
				class="h-1.5 w-1.5 animate-pulse
					rounded-full bg-green-500"
			></span>

			<span
				class="text-[9px] font-semibold uppercase
					tracking-[0.22em] text-black/45"
			>
				Always open to meaningful collaborations
			</span>

		</div>

	</div>

</section>


<style>
	.testimonial-row {
		animation: testimonial-scroll 35s linear infinite;
	}

	.testimonial-row-reverse {
		animation: testimonial-scroll-reverse 40s linear infinite;
	}

	.testimonial-row:hover,
	.testimonial-row-reverse:hover {
		animation-play-state: paused;
	}

	@keyframes testimonial-scroll {
		from {
			transform: translateX(0);
		}

		to {
			transform: translateX(-50%);
		}
	}

	@keyframes testimonial-scroll-reverse {
		from {
			transform: translateX(-50%);
		}

		to {
			transform: translateX(0);
		}
	}
</style>