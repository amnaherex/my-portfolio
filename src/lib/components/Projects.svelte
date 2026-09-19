<script lang="ts">
	const projects = [
		{
			number: '01',
			title: 'Project One',
			category: 'Full Stack',
			description:
				'A modern full-stack application focused on creating a fast, intuitive, and polished user experience.',
			technologies: ['Next.js', 'TypeScript', 'PostgreSQL'],
			image: '/project-1.png'
		},
		{
			number: '02',
			title: 'Project Two',
			category: 'Web Application',
			description:
				'A scalable web application combining thoughtful interface design with a reliable backend architecture.',
			technologies: ['React', 'Node.js', 'MongoDB'],
			image: '/project-2.png'
		},
		{
			number: '03',
			title: 'Project Three',
			category: 'Interactive',
			description:
				'An interactive digital experience built around smooth animations, responsive layouts, and modern frontend technologies.',
			technologies: ['SvelteKit', 'TypeScript', 'GSAP'],
			image: '/project-3.png'
		}
	];
</script>

<section
	id="work"
	class="relative min-h-screen overflow-hidden px-6 py-20 md:px-12 lg:px-20"
>
	<div class="mx-auto max-w-7xl">

		<!-- Section Header -->

		<div class="mb-10 grid items-end gap-10 md:grid-cols-[1fr_auto]">

            <!-- Left Content -->
        
            <div>
                <p
                    class="mb-5 text-xs font-medium uppercase tracking-[0.3em] text-black/50"
                >
                    Selected Work
                </p>
        
                <h2
                    class="max-w-4xl text-6xl font-semibold tracking-[-0.04em] text-black md:text-8xl"
                >
                    Things I've
                    <span class="font-serif-display italic">
                        built.
                    </span>
                </h2>
        
                <p
                    class="mt-8 max-w-xl text-base leading-7 text-black/50 md:text-lg"
                >
                    A collection of projects where design, development, and
                    technology come together to create meaningful digital
                    experiences.
                </p>
            </div>
        
        
            <!-- View All Projects -->
        
            <a
                href="/projects"
                class="group mb-2 flex w-fit items-center gap-4 rounded-full border border-black/10 bg-white/60 px-5 py-2.5 backdrop-blur-xl transition-all duration-300 hover:-translate-y-1 hover:bg-white hover:shadow-[0_15px_40px_rgba(0,0,0,0.1)]"
            >
                <span
                    class="text-xs font-semibold uppercase tracking-[0.18em] text-black"
                >
                    View All Projects
                </span>
        
                <span
                    class="flex h-9 w-9 items-center justify-center rounded-full bg-black text-white transition-transform duration-500 group-hover:rotate-45"
                >
                    ↗
                </span>
            </a>
        
        </div>


		<!-- Featured Projects -->

		<div class="space-y-5">

			{#each projects as project}

				<article
					class="group relative overflow-hidden rounded-[32px] border border-black/10 bg-white/50 p-5 backdrop-blur-xl transition-all duration-500 hover:-translate-y-2 hover:shadow-[0_30px_80px_rgba(0,0,0,0.12)] md:p-7"
				>

					<div
						class="grid items-center gap-10 lg:grid-cols-[0.8fr_1.2fr]"
					>

						<!-- Project Information -->

						<div class="flex h-full flex-col justify-between">

							<div>

								<!-- Number + Category -->

								<div
									class="mb-8 flex items-center justify-between"
								>

									<span
										class="text-xs font-medium tracking-[0.2em] text-black/40"
									>
										{project.number}
									</span>

									<span
										class="rounded-full border border-black/10 bg-white/60 px-3 py-1.5 text-[10px] uppercase tracking-[0.15em] text-black/50"
									>
										{project.category}
									</span>

								</div>


								<!-- Title -->

								<h3
									class="text-4xl font-semibold tracking-[-0.03em] text-black md:text-5xl"
								>
									{project.title}
								</h3>


								<!-- Description -->

								<p
									class="mt-5 max-w-lg text-sm leading-7 text-black/55 md:text-base"
								>
									{project.description}
								</p>


								<!-- Technologies -->

								<div class="mt-7 flex flex-wrap gap-2">

									{#each project.technologies as technology}

										<span
											class="rounded-full border border-black/10 bg-white/60 px-3 py-1.5 text-[10px] font-medium uppercase tracking-[0.12em] text-black/55"
										>
											{technology}
										</span>

									{/each}

								</div>

							</div>


							<!-- Project Link -->

							<a
								href="#"
								class="group/link mt-10 flex w-fit items-center gap-3 text-xs font-semibold uppercase tracking-[0.2em]"
							>
								View Project

								<span
									class="flex h-9 w-9 items-center justify-center rounded-full border border-black/10 bg-white transition-all duration-300 group-hover/link:rotate-45 group-hover/link:bg-black group-hover/link:text-white"
								>
									↗
								</span>

							</a>

						</div>


						<!-- Project Image -->

						<div
							class="relative aspect-[16/10] overflow-hidden rounded-[24px] bg-black/5"
						>

							<img
								src={project.image}
								alt={project.title}
								class="h-full w-full object-cover transition-transform duration-700 ease-out group-hover:scale-105"
							/>

						</div>

					</div>

				</article>

			{/each}

		</div>


        

	</div>
</section>