<!--

@component CenteredTextOnlyHero

This component displays a centered text hero with call to action buttons.
Takes up the full viewport height and centers content vertically.
-->

<script lang="ts">
	// Components
	import AnimateText from "$lib/components/animation/AnimateText.svelte";
	import Button from "$lib/components/ui/Button.svelte";

	// Constants
	import { cta } from "$lib/navigation";

	// Types
	type Props = {
		title: string;
		subtitle: string;
		callsToAction?: Array<{
			href: string;
			label: string;
		}>; // A maximum of two calls to action, with the first one being primary and the second one being secondary
	};

	let {
		title,
		subtitle,
		callsToAction = [cta],
		...rest
	}: Props = $props();
</script>

<div class="min-h-[calc(100vh-var(--nav-height))] flex items-center justify-center" {...rest}>
	<div class="bg-background w-full">
		<header
			class="section-px container mx-auto grid place-items-center text-center"
			data-enter-container
		>
			<div class="grid max-w-4xl place-items-center justify-center gap-8 py-20">
				<!-- Team alignment illustration -->
				<div class="w-32 h-20 opacity-60 mb-4" data-enter>
					<img 
						src="/generated/image-a-candid-moment-of-two-individuals-in-a-.webp" 
						alt="Team alignment illustration" 
						class="w-full h-full object-cover rounded-lg filter grayscale"
					/>
				</div>
				
				<h1 class="text-display w-full text-balance" data-enter>
					<span class="block"><AnimateText text={title} /></span>
				</h1>

				<p
					data-enter
					class="text-xl block max-w-2xl text-pretty text-muted-foreground leading-relaxed"
				>
					{subtitle}
				</p>

				{#if callsToAction.length > 0}
					<div class="mt-4 flex gap-4" data-enter>
						{#each callsToAction as cta, index}
							<Button href={cta.href} size="lg" variant={index === 0 ? "default" : "outline"}
								>{cta.label}</Button
							>
						{/each}
					</div>
				{/if}
			</div>
		</header>
	</div>
</div>
