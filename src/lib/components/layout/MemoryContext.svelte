<!--
@component MemoryContext

A section highlighting Sentra's real-time memory and global context capabilities
-->

<script lang="ts">
	import AnimateText from "../animation/AnimateText.svelte";

	type Props = {
		title: string;
		subtitle: string;
		description: string;
		features: string[];
		questions: string[];
		bottomText: string;
		teamCredentials: string;
		imageSrc: string;
	};

	let { 
		title, 
		subtitle, 
		description, 
		features, 
		questions, 
		bottomText, 
		teamCredentials,
		imageSrc 
	}: Props = $props();
</script>

<section class="section-py bg-background">
	<div class="container mx-auto section-px">
		<!-- Header -->
		<div class="text-center mb-16 max-w-4xl mx-auto">
			<div class="flex items-center justify-center gap-4 mb-8">
				{#each features as feature}
					<span class="px-4 py-2 bg-primary/10 text-primary rounded-full text-sm font-medium">
						{feature}
					</span>
				{/each}
			</div>
			
			<h2 class="text-display mb-6">
				<AnimateText text={title} />
			</h2>
			<p class="text-muted-foreground text-lg leading-relaxed">{description}</p>
		</div>

		<!-- Main Content Grid -->
		<div class="grid lg:grid-cols-2 gap-16 items-center mb-16 max-w-6xl mx-auto">
			<!-- Content -->
			<div>
				<h3 class="text-title1 mb-8">{subtitle}</h3>
				
				<div class="space-y-6 mb-8">
					<p class="text-muted-foreground leading-relaxed">
						Sentra doesn't build fixed dashboards or static docs. It builds understanding.
					</p>
					
					<p class="text-muted-foreground leading-relaxed">
						It draws just-in-time insights from meetings, chats, calendars, and direct 1:1 interaction with your team—capturing not just what happened, but how and why.
					</p>
				</div>

				<!-- Questions Section -->
				<div class="bg-muted/50 rounded-lg p-6">
					<h4 class="font-semibold mb-4 text-foreground">Questions Sentra asks your team:</h4>
					<ul class="space-y-3">
						{#each questions as question}
							<li class="flex items-start gap-3">
								<span class="text-primary font-bold">•</span>
								<span class="text-muted-foreground italic">"{question}"</span>
							</li>
						{/each}
					</ul>
				</div>
			</div>

			<!-- Visual -->
			<div class="relative">
				<div class="aspect-square rounded-xl overflow-hidden bg-muted">
					<img 
						src={imageSrc} 
						alt="Team members in individual conversations"
						class="w-full h-full object-cover"
					/>
				</div>
				
				<!-- Overlay text -->
				<div class="absolute inset-0 bg-black/40 rounded-xl flex items-center justify-center">
					<div class="text-center text-white p-6">
						<h4 class="text-xl font-semibold mb-2">1:1 Conversations</h4>
						<p class="text-sm opacity-90">Sentra talks to everyone individually</p>
					</div>
				</div>
			</div>
		</div>

		<!-- Bottom Section -->
		<div class="text-center max-w-4xl mx-auto">
			<p class="text-muted-foreground text-lg leading-relaxed mb-8">{bottomText}</p>
			
			<div class="bg-card border rounded-lg p-6">
				<p class="text-sm text-muted-foreground">{teamCredentials}</p>
			</div>
		</div>
	</div>
</section>