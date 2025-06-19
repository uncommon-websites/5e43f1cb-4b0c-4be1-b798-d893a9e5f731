<!--
@component AutonomyComparison

A side-by-side comparison section highlighting Sentra's autonomous approach vs traditional AI tools
-->

<script lang="ts">
	import AnimateText from "../animation/AnimateText.svelte";
	import Button from "../ui/Button.svelte";

	type Props = {
		title: string;
		subtitle: string;
		description: string;
		otherTools: {
			title: string;
			points: string[];
			imageSrc: string;
		};
		sentra: {
			title: string;
			points: string[];
			imageSrc: string;
		};
		bottomSection: {
			title: string;
			subtitle: string;
			description: string;
		};
	};

	let { 
		title, 
		subtitle, 
		description, 
		otherTools, 
		sentra, 
		bottomSection 
	}: Props = $props();
</script>

<section class="section-py bg-muted/30">
	<div class="container mx-auto section-px">
		<!-- Header -->
		<div class="text-center mb-16 max-w-3xl mx-auto">
			<h2 class="text-display mb-6">
				<AnimateText text={title} />
			</h2>
			<p class="text-title2 text-muted-foreground mb-4">{subtitle}</p>
			<p class="text-muted-foreground leading-relaxed">{description}</p>
		</div>

		<!-- Comparison Grid -->
		<div class="grid lg:grid-cols-2 gap-8 mb-16 max-w-6xl mx-auto">
			<!-- Other Tools -->
			<div class="bg-background border rounded-xl p-8 relative overflow-hidden">
				<div class="relative z-10">
					<h3 class="text-title1 mb-6 text-muted-foreground">{otherTools.title}</h3>
					<ul class="space-y-4 mb-8">
						{#each otherTools.points as point}
							<li class="flex items-start gap-3">
								<div class="w-2 h-2 bg-muted-foreground rounded-full mt-2 flex-shrink-0"></div>
								<span class="text-muted-foreground">{point}</span>
							</li>
						{/each}
					</ul>
				</div>
				
				<!-- Background Image -->
				<div class="absolute inset-0 opacity-20">
					<img 
						src={otherTools.imageSrc} 
						alt="Complex setup process"
						class="w-full h-full object-cover"
					/>
				</div>
			</div>

			<!-- Sentra -->
			<div class="bg-primary/5 border-2 border-primary/20 rounded-xl p-8 relative overflow-hidden">
				<div class="relative z-10">
					<h3 class="text-title1 mb-6 text-primary font-semibold">{sentra.title}</h3>
					<ul class="space-y-4 mb-8">
						{#each sentra.points as point}
							<li class="flex items-start gap-3">
								<div class="w-2 h-2 bg-primary rounded-full mt-2 flex-shrink-0"></div>
								<span class="text-foreground">{point}</span>
							</li>
						{/each}
					</ul>
				</div>
				
				<!-- Background Image -->
				<div class="absolute inset-0 opacity-10">
					<img 
						src={sentra.imageSrc} 
						alt="Simple setup process"
						class="w-full h-full object-cover"
					/>
				</div>
			</div>
		</div>

		<!-- Bottom Section -->
		<div class="text-center max-w-4xl mx-auto">
			<h3 class="text-title1 mb-4">
				<AnimateText text={bottomSection.title} />
			</h3>
			<p class="text-title2 text-muted-foreground mb-6">{bottomSection.subtitle}</p>
			<p class="text-muted-foreground leading-relaxed mb-8">{bottomSection.description}</p>
			
			<Button size="lg" href="/request-access">
				Hire Sentra today
			</Button>
		</div>
	</div>
</section>