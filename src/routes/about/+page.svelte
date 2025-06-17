<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
    {
      title: "We listen quietly, act early",
      description: "Great teams don’t ignore quiet signals. Sentra surfaces small signs of misalignment before they become big problems."
    },
    {
      title: "Connect across every corner",
      description: "Clear communication drives alignment. We believe every team’s perspective matters in keeping organizations healthy."
    },
    {
      title: "Trust through transparency",
      description: "Sentra’s alerts are always privacy-first—focused on patterns, not individuals—so you get signal, not surveillance."
    },
    {
      title: "Proactive, not reactive",
      description: "We value early, subtle intervention over fire drills. Sentra helps you address problems before people feel them."
    }
  ];
</script>

<SecondaryHero
	title="Stay ahead of team misalignment"
	subtitle="Sentra alerts you to collaboration issues before they become problems"
	imageSrc="/mockups/airport-screen-1750178260373.png"
/>

<!-- Story Section -->
<Story
  paragraphs={[
    "Sentra started with a question: why do teams go off track, even when everyone’s trying their best? We spoke to leaders of growing companies and kept hearing the same thing—internal misalignment doesn't arrive with a bang; it builds quietly. People speak up less in meetings, updates get delayed, and cross-team communication feels harder than it should be. These early signs are typically missed until the damage is done.",
    "That was the 'aha' moment. What if an AI could catch subtle changes in team dynamics—like quiet disengagement or mounting friction—before they lead to lost momentum or confusion? Sentra became that AI teammate. It listens across existing tools, connects the dots, and gives leaders a heads-up that something’s slipping—not with guesswork, but with real signals they may not notice in time.",
    "Pilot teams using Sentra reported big gains in clarity and efficiency. They trimmed unnecessary meetings, cut friction between departments, and acted on alignment risks early. No extra dashboards, no complicated setup—just simple, proactive insight when it’s needed most."
  ]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
  stakeholderType="team"
  title="Meet Sentra’s founder."
  subtitle="Building proactive alignment from the inside out."
  stakeholders={[
    {
      name: "Alex Morgan",
      position: "Founder & CEO",
      bio: "Founded Sentra to help organizations spot misalignment issues early—before they become costly or irreversible. Passionate about organizational health, Alex applies deep experience in team collaboration and AI to solve real workplace challenges.",
      image: "/generated/image-a-professional-headshot-of-a-serious-bus.webp"
    }
  ]}
/>

<StakeholderGrid
	stakeholderType="investor"
	title="Backed by the best."
	subtitle="Point Nine, TSIC and others"
	stakeholders={[
		{
			name: "Point Nine Capital",
			image: "https://cdn.brandfetch.io/pointnine.com/w/400/h/400/logo?c=1id_elLz2Bd5Ej-dWo7"
		},
		{
			name: "TSIC Ventures",
			image: "https://cdn.brandfetch.io/tiny.vc/w/400/h/400/logo?c=1a2b3c4d5e"
		},
		{
			name: "Sequoia Capital",
			image: "https://cdn.brandfetch.io/sequoiacap.com/w/400/h/400/logo"
		}
	]}
/>

<!-- CTA Section -->
<CallToAction
  title="Be the first to spot misalignment."
  subtitle="Sentra is invite-only for now."
  description="Join our private beta to get early access to an AI teammate that helps your team stay aligned—before problems arise. Bring new clarity, save time, and prevent team friction before it starts. The future of proactive teamwork starts here."
  imageSrc="/generated/image-a-group-of-diverse-professionals-engaged.webp"
  callsToAction={[
    { href: '/request-access', label: 'Request early access', variant: 'primary' }
  ]}
/>
