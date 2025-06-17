<script lang="ts">
	import type { HTMLAttributes } from "svelte/elements";
	const props: HTMLAttributes<SVGSVGElement> = $props();
</script>

<svg viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="" {...props}>
	<!-- Sentra Logo: Interconnected nodes representing organizational alignment -->
	<circle cx="6" cy="6" r="2.5" fill="currentColor" opacity="0.8"/>
	<circle cx="18" cy="6" r="2.5" fill="currentColor" opacity="0.8"/>
	<circle cx="6" cy="18" r="2.5" fill="currentColor" opacity="0.8"/>
	<circle cx="18" cy="18" r="2.5" fill="currentColor" opacity="0.8"/>
	<circle cx="12" cy="12" r="3" fill="currentColor"/>
	
	<!-- Connection lines showing alignment -->
	<path d="M8.5 6L9.5 12" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
	<path d="M15.5 6L14.5 12" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
	<path d="M6 8.5L12 9.5" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
	<path d="M18 8.5L12 9.5" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
	<path d="M8.5 18L9.5 12" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
	<path d="M15.5 18L14.5 12" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
	<path d="M6 15.5L12 14.5" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
	<path d="M18 15.5L12 14.5" stroke="currentColor" stroke-width="1.5" opacity="0.6"/>
</svg>
