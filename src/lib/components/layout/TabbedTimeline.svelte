<!--
@component TabbedTimeline

A tabbed timeline component showing different workflows for organizations vs individuals
Features smooth transitions and magnification effects when sections are centered
-->

<script lang="ts">
	import { onMount } from "svelte";
	import { scroll, animate } from "motion";
	import Button from "../ui/Button.svelte";
	import AnimateText from "../animation/AnimateText.svelte";

	type Badge = "Leaders" | "Everyone";
	
	type TimelineStep = {
		title: string;
		description: string;
		visual: string;
		badges?: Badge[];
		imageSrc?: string;
	};

	type Tab = {
		id: string;
		label: string;
		subtitle: string;
		steps: TimelineStep[];
		cta: {
			title: string;
			description: string;
			buttonText: string;
			imageSrc?: string;
		};
	};

	type Props = {
		title: string;
		tabs: Tab[];
		defaultTab?: string;
	};

	let { title, tabs, defaultTab = tabs[0]?.id }: Props = $props();

	let activeTab = $state(defaultTab);
	let containerElement: HTMLDivElement;

	let currentTab = $derived(tabs.find(tab => tab.id === activeTab) || tabs[0]);

	function switchTab(tabId: string) {
		activeTab = tabId;
	}

	onMount(() => {
		if (!containerElement) return;
		if (window.self !== window.top) return;

		// Set up intersection observer for step animations
		const stepElements = containerElement.querySelectorAll('.timeline-step');
		
		const observer = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						entry.target.classList.add('in-view');
					}
				});
			},
			{ threshold: 0.6, rootMargin: '-20% 0px -20% 0px' }
		);

		stepElements.forEach((el) => observer.observe(el));

		return () => observer.disconnect();
	});
</script>

<section class="section-py bg-background" bind:this={containerElement}>
	<div class="container mx-auto section-px">
		<!-- Section Header -->
		<div class="text-center mb-16">
			<h2 class="text-display mb-8">
				<AnimateText text={title} />
			</h2>
			
			<!-- Tab Switcher -->
			<div class="inline-flex bg-muted rounded-lg p-1 mb-8">
				{#each tabs as tab}
					<button
						class="px-6 py-3 rounded-md transition-all duration-300 font-medium"
						class:bg-background={activeTab === tab.id}
						class:shadow-sm={activeTab === tab.id}
						class:text-foreground={activeTab === tab.id}
						class:text-muted-foreground={activeTab !== tab.id}
						onclick={() => switchTab(tab.id)}
					>
						{tab.label}
					</button>
				{/each}
			</div>
		</div>

		<!-- Timeline Content -->
		{#if currentTab}
			<div class="max-w-6xl mx-auto">
				<h3 class="text-title1 text-center mb-16 text-muted-foreground">
					{currentTab.subtitle}
				</h3>

				<!-- Timeline Steps -->
				<div class="space-y-24">
					{#each currentTab.steps as step, index}
						<div class="timeline-step grid lg:grid-cols-2 gap-12 items-center transition-all duration-700 opacity-60 scale-95">
							<!-- Content -->
							<div class="order-2 lg:order-1" class:lg:order-2={index % 2 === 1}>
								<div class="flex items-center gap-3 mb-4">
									<span class="flex items-center justify-center w-8 h-8 bg-primary text-primary-foreground rounded-full text-sm font-bold">
										{index + 1}
									</span>
									{#if step.badges}
										<div class="flex gap-2">
											{#each step.badges as badge}
												<span class="px-2 py-1 bg-muted text-muted-foreground text-xs rounded-full font-medium">
													{badge}
												</span>
											{/each}
										</div>
									{/if}
								</div>
								
								<h4 class="text-title2 mb-4">{step.title}</h4>
								<p class="text-muted-foreground leading-relaxed">{step.description}</p>
							</div>

							<!-- Visual -->
							<div class="order-1 lg:order-2" class:lg:order-1={index % 2 === 1}>
								{#if step.imageSrc}
									<div class="relative overflow-hidden rounded-lg bg-muted aspect-video">
										<img 
											src={step.imageSrc} 
											alt={step.title}
											class="w-full h-full object-cover transition-transform duration-700"
										/>
									</div>
								{:else}
									<div class="bg-muted rounded-lg p-8 aspect-video flex items-center justify-center">
										<p class="text-muted-foreground text-center">{step.visual}</p>
									</div>
								{/if}
							</div>
						</div>
					{/each}
				</div>

				<!-- CTA Section -->
				<div class="mt-24 bg-card border rounded-xl p-8 lg:p-12">
					<div class="grid lg:grid-cols-2 gap-8 items-center">
						<div>
							<h3 class="text-title1 mb-4">{currentTab.cta.title}</h3>
							<p class="text-muted-foreground mb-6 leading-relaxed">{currentTab.cta.description}</p>
							<Button size="lg" href="/request-access">
								{currentTab.cta.buttonText}
							</Button>
						</div>
						{#if currentTab.cta.imageSrc}
							<div class="relative overflow-hidden rounded-lg">
								<img 
									src={currentTab.cta.imageSrc} 
									alt="CTA visual"
									class="w-full h-full object-cover aspect-video lg:aspect-square"
								/>
							</div>
						{/if}
					</div>
				</div>
			</div>
		{/if}
	</div>
</section>

<style>
	.timeline-step.in-view {
		opacity: 1;
		transform: scale(1.02);
	}
	
	.timeline-step.in-view img {
		transform: scale(1.05);
	}
</style>