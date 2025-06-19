<!-- This file can be deleted -->
	// Components
	import SlideshowHero from "$lib/components/layout/hero-sections/SlideshowHero.svelte";
	import TabbedTimeline from "$lib/components/layout/TabbedTimeline.svelte";
	import AutonomyComparison from "$lib/components/layout/AutonomyComparison.svelte";
	import MemoryContext from "$lib/components/layout/MemoryContext.svelte";
	import ROISection from "$lib/components/layout/ROISection.svelte";
</script>

<!-- Hero Slideshow -->
<SlideshowHero 
	slides={[
		{
			title: "When teams scale fast, everyone ends up on different pages of the same book."
		},
		{
			title: "Sentra keeps everyone aligned",
			subtitle: "A proactive teammate you don't have to chase"
		}
	]}
/>

<!-- How It Works Section -->
<TabbedTimeline 
	title="What it's like to work with Sentra"
	tabs={[
		{
			id: "organizations",
			label: "For organizations",
			subtitle: "Keeping everything together",
			steps: [
				{
					title: "Add Sentra to the platforms you use",
					description: "Sentra integrates seamlessly into tools like Zoom, Slack, and Google Calendar—no process changes required.",
					visual: "Integration selection interface",
					badges: ["Leaders"],
					imageSrc: "/generated/image-a-diverse-business-team-engaged-in-a-tho.webp"
				},
				{
					title: "Share your calendars",
					description: "One-time sync and Sentra knows where to show up.",
					visual: "Calendar sync interface",
					imageSrc: "/generated/image-a-professional-woman-in-an-office-settin.webp"
				},
				{
					title: "Get briefed before every event",
					description: "Walk into meetings with full context—Sentra surfaces relevant research, recent discussions, and shared agendas.",
					visual: "Pre-meeting briefing",
					badges: ["Everyone"],
					imageSrc: "/generated/image-a-business-meeting-preparation-scene-wit.webp"
				},
				{
					title: "Never forget what you said you'd do",
					description: "Sentra captures in-meeting commitments and follows up with task reminders.",
					visual: "Task tracking and reminders",
					badges: ["Everyone"],
					imageSrc: "/generated/image-a-person-standing-near-a-window-holding-.webp"
				},
				{
					title: "Know who your company's already met",
					description: "Sentra sends you insights like \"Jae met with AstraZeneca a month ago—they signed an NDA.\"",
					visual: "Meeting history insights",
					badges: ["Everyone"],
					imageSrc: "/generated/image-two-professionals-meeting-for-the-first-.webp"
				},
				{
					title: "Get alerted when important things shift",
					description: "No more surprise deadline changes. Sentra sends real-time updates from meetings you missed.",
					visual: "Real-time notifications",
					badges: ["Everyone"],
					imageSrc: "/generated/image-notification-alert-on-smartphone-busines.webp"
				},
				{
					title: "Have insight into how decisions got made",
					description: "Sentra builds a dynamic view of how projects evolve over time and why certain paths were taken.",
					visual: "Decision timeline visualization",
					badges: ["Everyone"],
					imageSrc: "/generated/image-timeline-visualization-business-decision.webp"
				},
				{
					title: "Sentra checks in regularly",
					description: "Daily calls with Sentra help you surface blockers, organize priorities, and stay clear on next steps.",
					visual: "Regular check-in calls",
					badges: ["Everyone"],
					imageSrc: "/generated/image-professional-phone-call-business-convers.webp"
				}
			],
			cta: {
				title: "Sentra is your real-time alignment partner",
				description: "The faster your company grows, the more critical that becomes.",
				buttonText: "Hire Sentra today",
				imageSrc: "/generated/image-notification-alert-on-smartphone-busines.webp"
			}
		},
		{
			id: "individuals",
			label: "For individuals",
			subtitle: "Your best executive assistant",
			steps: [
				{
					title: "Connect your calendar, get a dedicated line for Sentra",
					description: "Sentra plugs directly into your workflow and is always just a text away.",
					visual: "Calendar and phone integration",
					imageSrc: "/generated/image-organized-workspace-calendar-phone-conne.webp"
				},
				{
					title: "Know exactly what to expect in every meeting",
					description: "Pre-meeting messages give you the latest updates, feedback, and context.",
					visual: "Meeting preparation briefings",
					imageSrc: "/generated/image-a-business-meeting-preparation-scene-wit.webp"
				},
				{
					title: "Never forget what you promised",
					description: "Sentra tracks what you commit to and follows up before it falls through the cracks.",
					visual: "Personal task tracking",
					imageSrc: "/generated/image-a-person-standing-near-a-window-holding-.webp"
				},
				{
					title: "Set and track your personal goals",
					description: "Build habits, push career milestones—Sentra keeps your goals in clear view.",
					visual: "Goal tracking interface",
					imageSrc: "/generated/image-goal-setting-notebook-planning-personal-.webp"
				},
				{
					title: "Sentra calls you for guided end-of-day check-ins",
					description: "Decompress. Prioritize. Reset for tomorrow.",
					visual: "Daily reflection calls",
					imageSrc: "/generated/image-professional-phone-call-business-convers.webp"
				}
			],
			cta: {
				title: "Organize your life toward your goals",
				description: "Sentra helps you focus on what actually moves the needle",
				buttonText: "Hire Sentra today",
				imageSrc: "/generated/image-organized-life-goals-achievement-success.webp"
			}
		}
	]}
	defaultTab="organizations"
/>

<!-- Autonomy Section -->
<AutonomyComparison 
	title="Autonomy like never before"
	subtitle="They need setup. You just start."
	description="You don't have to chase Sentra. It's already on it."
	otherTools={{
		title: "Other AI tools",
		points: [
			"Require ongoing prompting and task definitions",
			"Demand steep onboarding and setup time",
			"Feel more like software than support"
		],
		imageSrc: "/generated/image-complex-software-setup-screens-overwhelm.webp"
	}}
	sentra={{
		title: "Sentra",
		points: [
			"Understands and acts from day one",
			"No training, installs, or manual prompting",
			"Works like a human teammate—asks when it needs to, updates when it should"
		],
		imageSrc: "/generated/image-simple-one-click-setup-clean-interface.webp"
	}}
	bottomSection={{
		title: "Understand. Update. Remind. Act. Without asking.",
		subtitle: "You hire Sentra. The work starts.",
		description: ""
	}}
/>

<!-- Memory Context Section -->
<MemoryContext 
	title="Memory with global context"
	subtitle="Your company runs on meetings and messages. So does Sentra."
	description="Sentra doesn't build fixed dashboards or static docs. It builds understanding. This isn't plug-and-play integration. This is live, distributed intelligence."
	features={["Real-time memory", "Company-wide awareness", "One teammate for it all"]}
	questions={[
		"What got in your way this week?",
		"What still doesn't make sense?",
		"Do we need to reconsider this deadline?",
		"What's blocking you right now?"
	]}
	bottomText="It draws just-in-time insights from meetings, chats, calendars, and direct 1:1 interaction with your team—capturing not just what happened, but how and why."
	teamCredentials="Created by a founding team with experience building agentic memory and context systems. Sentra adds a new dimension to how organizations think and align in real time."
	imageSrc="/generated/image-team-members-having-individual-conversat.webp"
/>

<!-- ROI Section -->
<ROISection 
	title="Companies struggle with scaling effectively"
	subtitle="Every founder dreads it"
	description="As your company grows, context disappears. Communication falters. People fall out of sync. And by the time you notice, the damage is already done. Sentra exists to prevent that. It becomes the connective tissue of your company—without disrupting how people already work."
	problems={[
		"Context disappears as teams grow",
		"Communication becomes fragmented",
		"People fall out of sync",
		"Problems surface too late"
	]}
	solutions={[
		"Self-heal",
		"Self-reflect", 
		"Stay aligned"
	]}
	imageSrc="/generated/image-business-growth-scaling-company-expansio.webp"
/>