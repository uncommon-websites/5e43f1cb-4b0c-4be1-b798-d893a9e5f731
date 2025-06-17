<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CenteredTextOnlyHero from "$lib/components/layout/hero-sections/CenteredTextOnlyHero.svelte";
</script>

<CenteredTextOnlyHero
  title="Know when your team’s not aligned"
  subtitle="Sentra alerts you when team participation drops or communication breaks down—so you can fix issues before they become problems."
  callsToAction={[{ href: '/request-access', label: 'Request early access' }]}
/>
<LogoScroller
	label="Trusted by industry leaders"
	logoUrls={[
		"https://logo.clearbit.com/atlassian.com",
		"https://logo.clearbit.com/slack.com",
		"https://logo.clearbit.com/zendesk.com",
		"https://logo.clearbit.com/zoom.us"
	]}
/>

<Summary
	title="What we do"
	text="Sentra is an AI teammate that helps companies stay aligned. It listens for signs of misalignment—like dropping participation or team conflicts—so you can fix problems before they escalate. Get clear, early signals to keep your team on track."
/>

<Testimonials
	testimonials={[
		{
			name: "Maria Nevarez",
			position: "Operations Lead",
			company: "Pacific Core Labs",
			quote:
				"Sentra shaved nearly five hours off our team meetings every week—without us losing track of a thing.",
			image: "/generated/image-confident-latina-businesswoman-working-i.webp"
		},
		{
			name: "Tobias Müller",
			position: "Head of Engineering",
			company: "Riverside Systems",
			quote:
				"An early alert from Sentra gave us enough time to clarify a cross-team mix-up that could have cost us a major account.",
			image: "/generated/image-a-cheerful-german-businessman-in-a-moder.webp"
		},
		{
			name: "Riley Kim",
			position: "People & Culture Manager",
			company: "Nebula Interactive",
			quote:
				"Cutting even a few unnecessary meetings with Sentra’s help saved us thousands each quarter. The results are in our budget.",
			image: "/generated/image-a-nonbinary-asian-professional-sitting-i.webp"
		}
	]}
/>

<Features
	title="Why teams choose Sentra"
	subtitle="Six ways Sentra tackles misalignment before it affects your business."
	features={[
		{
			title: "Proactive misalignment detection",
			description: "Sentra quietly analyzes activity and flags disengagement and collaboration issues before anyone asks about morale."
		},
		{
			title: "Reduced unnecessary meetings",
			description: "Identify when meetings lose value and cut them back without second-guessing—or guesswork."
		},
		{
			title: "Early alerting for silent resignation",
			description: "Spot team members who have stopped participating, updating, or collaborating long before it becomes a problem."
		},
		{
			title: "Cross-team communication health",
			description: "Get notified when teams begin working in silos or communication breaks down between key groups."
		},
		{
			title: "Privacy-respecting analysis",
			description: "Sentra respects boundaries, learning norms and signals without exposing private conversations."
		},
		{
			title: "Continuous learning AI teammate",
			description: "Sentra adapts to your company’s unique rhythm for truly relevant, actionable organizational insight."
		}
	]}
/>

<UseCases
	title="Use cases"
	subtitle="Real-world applications for your business needs"
	useCases={[
		{
			title: "Catch silent resignation",
			description: "Get notified when engagement drops so you can re-engage teammates before they drift away.",
			image: "/generated/image-a-diverse-team-in-an-office-setting-with.webp",
			link: {
				href: "/use-cases/silent-resignation",
				label: "Learn more"
			}
		},
		{
			title: "Reduce unnecessary meetings",
			description: "Spot recurring meetings with low participation and reclaim lost time with real data.",
			image: "/generated/image-a-manager-standing-alone-in-a-meeting-ro.webp",
			link: {
				href: "/use-cases/meeting-optimization",
				label: "Learn more"
			}
		},
		{
			title: "Detect team silos early",
			description: "Get ahead of cross-functional friction by identifying breakdowns in communication flow proactively.",
			image: "/generated/image-multiple-teams-working-in-a-spacious-ope.webp",
			link: {
				href: "/use-cases/team-silos",
				label: "Learn more"
			}
		}
	]}
/>

<AboutTeaser />
<CallToAction
  title="Keep your team aligned before problems surface"
  subtitle="Request exclusive early access"
  description="Sentra flags misalignment before it hurts your team—so you can act on issues early, cut back wasted meetings, and improve collaboration. Join our private beta to see the impact yourself."
  imageSrc="/generated/image-a-group-of-happy-smiling-business-profes.webp"
  callsToAction={[
    { href: '/request-access', label: 'Request early access', variant: 'primary' },
    { href: '/how-it-works', label: 'See how it works', variant: 'secondary' }
  ]}
/>
