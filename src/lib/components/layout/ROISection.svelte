<!--
@component ROISection

A section highlighting the ROI and value proposition of Sentra for scaling companies
-->

<script lang="ts">
	import AnimateText from "../animation/AnimateText.svelte";
	import Button from "../ui/Button.svelte";

	type Props = {
		title: string;
		subtitle: string;
		description: string;
		problems: string[];
		solutions: string[];
		imageSrc: string;
	};

	let { 
		title, 
		subtitle, 
		description, 
		problems, 
		solutions,
		imageSrc 
	}: Props = $props();
</script>

<section class="section-py bg-muted/20">
	<div class="container mx-auto section-px">
		<!-- Header -->
		<div class="text-center mb-16 max-w-4xl mx-auto">
			<h2 class="text-display mb-6">
				<AnimateText text={title} />
			</h2>
			<p class="text-title2 text-muted-foreground mb-8">{subtitle}</p>
		</div>

		<!-- Main Content -->
		<div class="grid lg:grid-cols-2 gap-16 items-center mb-16 max-w-6xl mx-auto">
			<!-- Content -->
			<div>
				<p class="text-muted-foreground text-lg leading-relaxed mb-8">{description}</p>
				
				<!-- Problems -->
				<div class="mb-8">
					<h3 class="text-title2 mb-4 text-muted-foreground">The problems that emerge:</h3>
					<ul class="space-y-3">
						{#each problems as problem}
							<li class="flex items-start gap-3">
								<span class="text-destructive font-bold mt-1">×</span>
								<span class="text-muted-foreground">{problem}</span>
							</li>
						{/each}
					</ul>
				</div>

				<!-- Solutions -->
				<div class="mb-8">
					<h3 class="text-title2 mb-4 text-primary">Sentra helps organizations:</h3>
					<ul class="space-y-3">
						{#each solutions as solution}
							<li class="flex items-start gap-3">
								<span class="text-primary font-bold mt-1">✓</span>
								<span class="text-foreground font-medium">{solution}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="bg-primary/5 border border-primary/20 rounded-lg p-6 mb-8">
					<p class="text-primary font-medium text-center">
						Before things go off the rails<br>
						Before misalignment becomes dysfunction<br>
						Before opportunity is missed
					</p>
				</div>

				<div class="text-center">
					<Button size="lg" href="/request-access">
						Hire Sentra today
					</Button>
					<p class="text-sm text-muted-foreground mt-3">And keep your company growing the right way</p>
				</div>
			</div>

			<!-- Visual -->
			<div class="relative">
				<div class="aspect-video rounded-xl overflow-hidden bg-muted">
					<img 
						src={imageSrc} 
						alt="Business growth and scaling"
						class="w-full h-full object-cover"
					/>
				</div>
				
				<!-- Overlay gradient -->
				<div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent to-transparent rounded-xl"></div>
				
				<!-- Overlay text -->
				<div class="absolute bottom-6 left-6 text-white">
					<h4 class="text-xl font-semibold mb-1">Scale with confidence</h4>
					<p class="text-sm opacity-90">Growth without the growing pains</p>
				</div>
			</div>
		</div>
	</div>
</section>