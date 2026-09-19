<script lang="ts">
	import Hero from '$lib/sections/Hero.svelte';
	import Capabilities from '$lib/components/Capabilities.svelte';
	import Projects from '$lib/components/Projects.svelte';
	import About from '$lib/components/About.svelte';
  import TechStack from '$lib/components/TechStack.svelte';
  import Testimonials from '$lib/components/Testimonials.svelte';
</script>


<main>

	<section id="home">
		<Hero />
	</section>


	<section id="work">
		<Capabilities />
	</section>


	<section id="projects">
		<Projects />
	</section>
	<section id="techstack">
		<TechStack/>
	</section>


	<section id="about">
		<About />
	</section>
	<section id="testimonials">
		<Testimonials />
	</section>



</main>