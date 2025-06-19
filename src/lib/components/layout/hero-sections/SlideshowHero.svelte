<!--
@component SlideshowHero

A slideshow hero section with scroll-triggered slides inspired by Superpower.com
Features bold white text on black background with smooth transitions
-->

<script lang="ts">
	import { onMount } from "svelte";
	import { scroll, animate } from "motion";
	import AnimateText from "$lib/components/animation/AnimateText.svelte";

	type Slide = {
		title: string;
		subtitle?: string;
	};

	type Props = {
		slides: Slide[];
	};

	let { slides }: Props = $props();

	let containerElement: HTMLDivElement;
	let currentSlide = $state(0);
	let isScrolling = $state(false);

	onMount(() => {
		if (!containerElement) return;
		if (window.self !== window.top) return;

		const slideElements = containerElement.querySelectorAll('.slide');
		
		// Set up scroll-triggered animations
		scroll(
			(progress) => {
				const slideCount = slides.length;
				const slideProgress = progress * (slideCount - 1);
				const newSlide = Math.min(Math.floor(slideProgress), slideCount - 1);
				
				if (newSlide !== currentSlide) {
					currentSlide = newSlide;
				}
			},
			{
				target: containerElement,
				offset: ["start start", "end start"]
			}
		);
	});
</script>

<div 
	bind:this={containerElement}
	class="relative h-[200vh] bg-black text-white overflow-hidden"
>
	<!-- Fixed viewport container -->
	<div class="sticky top-0 h-screen flex items-center justify-center">
		<div class="container mx-auto px-8 text-center">
			{#each slides as slide, index}
				<div 
					class="slide absolute inset-0 flex flex-col items-center justify-center transition-opacity duration-1000 ease-out"
					class:opacity-100={currentSlide === index}
					class:opacity-0={currentSlide !== index}
				>
					<h1 class="text-6xl md:text-8xl font-bold mb-8 max-w-5xl leading-tight">
						<AnimateText text={slide.title} />
					</h1>
					{#if slide.subtitle}
						<div class="text-xl md:text-2xl text-gray-300 max-w-2xl">
							<div class="text-3xl md:text-4xl font-semibold mb-2">
								<AnimateText text={slide.subtitle.split('\n')[0]} />
							</div>
							<div class="text-lg md:text-xl opacity-80">
								<AnimateText text={slide.subtitle.split('\n')[1]} />
							</div>
						</div>
					{/if}
				</div>
			{/each}
		</div>
	</div>
	
	<!-- Progress indicator -->
	<div class="fixed bottom-8 left-1/2 transform -translate-x-1/2 flex space-x-2 z-10">
		{#each slides as _, index}
			<div 
				class="w-2 h-2 rounded-full transition-all duration-300"
				class:bg-white={currentSlide === index}
				class:bg-gray-500={currentSlide !== index}
			></div>
		{/each}
	</div>
</div>

<style>
	.slide {
		pointer-events: none;
	}
	
	.slide.opacity-100 {
		pointer-events: auto;
	}
</style>