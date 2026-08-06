<script lang="ts">
	import { onMount } from 'svelte';
let gsap: typeof import('gsap').gsap;

	let card: HTMLDivElement;
 let subtitle :HTMLParagraphElement	
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

	const shapes = gsap.utils.toArray<HTMLElement>('.floating-shape');

	shapes.forEach((shape, index) => {
		gsap.from(shape, {
			y: -80,
			opacity: 0,
			scale: 0,
			rotation: gsap.utils.random(-180, 180),
			duration: 1,
			delay: index * 0.15,
			ease: 'back.out(1.7)'
		});

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
	function handleMouseLeave() {
	gsap.to(card, {
		rotateX: 0,
		rotateY: 0,
		duration: 0.8,
		ease: "power3.out"
	});
}
	function handleMouseMove(event: MouseEvent) {
		const rect = card.getBoundingClientRect();

		const x = event.clientX - rect.left;
		const y = event.clientY - rect.top;

		const centerX = rect.width / 2;
		const centerY = rect.height / 2;

		const rotateY = ((x - centerX) / centerX) * 15;
		const rotateX = -((y - centerY) / centerY) * 15;

		// Tilt the card
		gsap.to(card, {
			rotateX,
			rotateY,
			duration: 0.25,
			ease: 'power3.out'
		});

		// Move all floating shapes slightly
		
	}

	

		
	
</script>

<section
	class="relative flex min-h-screen items-center justify-center overflow-hidden bg-gradient-to-br from-white via-stone-50 to-gray-100"
>	
	<div
	class="pointer-events-none absolute inset-0"
	style="
	background:
	radial-gradient(circle,transparent 55%,rgba(0,0,0,.08));
"
></div>
	<div
	class="absolute inset-0 opacity-[0.02]"
	style="
	background-image:
	linear-gradient(to right,#000 1px,transparent 1px),
	linear-gradient(to bottom,#000 1px,transparent 1px);
	background-size:60px 60px;
"
>
</div>
	<!-- Grain Overlay -->
    <div
        class="pointer-events-none absolute inset-0 z-0 opacity-[0.1]"
        style="
            background-image:
                radial-gradient(#000 0.10px, transparent 0.05px);
            background-size: 4px 4px;
        "
    ></div>
	<div
	class="absolute left-1/2 top-1/2 h-[700px] w-[700px] -translate-x-1/2 -translate-y-1/2 rounded-full bg-amber-100/30 blur-[130px]"
></div>
<div
class="absolute -left-32 top-20 h-96 w-96 rounded-full bg-pink-500/20 blur-[120px]"
></div>

<div
class="absolute -right-32 bottom-10 h-96 w-96 rounded-full bg-cyan-500/20 blur-[120px]"
></div>
	<!-- Floating Star -->

	<img
	src="/star-black.png"
	alt="black star"
	class="floating-shape absolute right-[20%] top-[20%] z-20 w-36 "
/>	

<img
	src="/shape2.png"
	alt="cylinder"
	class="floating-shape absolute left-[12%] top-[20%] z-20 w-40"
/>

<img
	src="/shape3.png"
	alt="circle"
	class="floating-shape absolute left-[18%] bottom-[10%] z-20 w-44"
/>
<img
	src="/shape4.png"
	alt=""
	class="floating-shape absolute right-[18%] bottom-[10%] z-20 w-40"
/>

<img
	src="/shape5.png"
	alt="blue star"
	class="floating-shape absolute left-[10%] top-[46%] z-20 w-44"
/>


<img
	src="/shape6.png"
	alt=""
	class="floating-shape absolute right-[10%] top-[44%] z-20 w-44"
/>
	<!-- Background Text -->

	<h1
		class="pointer-events-none absolute mt-10 flex flex-col text-center font-black uppercase leading-[0.85] text-black/10 select-none"
	>
		<span class="text-[13rem]">Software</span>
		<span class="text-[12rem]">Developer</span>
	</h1>

	<!-- Hero Content -->

	<div class="relative z-30 flex flex-col items-center gap-4 text-center">

		<p class="text-5xl font-extrabold text-black">
			Hi I'm
			<span class="font-serif-display text-6xl italic">
				Amna!
			</span>
		</p>

		<p class="text-md text-gray-500">
			Full Stack Web Developer
		</p>

		<div class="[perspective:1200px]">

			<!-- svelte-ignore a11y_no_static_element_interactions -->
			<div
				bind:this={card}
				onmousemove={handleMouseMove}
				onmouseleave={handleMouseLeave}
				class="h-[380px] w-[320px] overflow-hidden rounded-[32px] shadow-2xl will-change-transform"
				style="transform-style:preserve-3d;"
			>
				<img
				src="/amna.jpg"
				alt="Amna Amjad"
				class="h-full w-full object-cover"
				style="transform: translateZ(40px);"
			/>
			</div>

		</div>

		<button
			class="rounded-full bg-white px-8 py-4 text-lg font-semibold shadow-xl transition hover:-translate-y-1 hover:shadow-2xl"
		>
			Let's Work Together
		</button>

	</div>
</section>