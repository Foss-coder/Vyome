<script lang="ts">
import GlassCard from '$lib/components/GlassCard.svelte';
import BlueprintIcon from '$lib/components/BlueprintIcon.svelte';
import StatusPulse from '$lib/components/StatusPulse.svelte';
</script>

<section class="hero-panel">
	<div>
		<div class="hero-meta">
			<span class="status-badge"><span class="status-dot"></span>SYSTEM: ARCHITECTED</span>
			<span class="status-badge">[ MASTER ARCHITECT ]</span>
		</div>

		<h1 class="hero-title">We architect high-end digital ecosystems</h1>
		<p class="hero-copy">
			For luxury resorts, boutique fashion houses, premium real estate, and architectural practices that demand technical precision and editorial craft.
		</p>

		<div class="hero-actions">
			<a class="cta-link" href="/work">Explore Work</a>
			<a class="cta-link" href="/services">View Services</a>
		</div>
	</div>

	<GlassCard class="glass-compact">
		<div class="status-badge">[ ATELIER SYNOPSIS ]</div>
		<h2 class="card-heading">The Digital Atelier for premium experiences</h2>
		<p class="card-copy">We translate architectural discipline into digital systems using a restrained visual language, abundant whitespace, and glassmorphic structures that feel crafted, not manufactured.</p>
	</GlassCard>
</section>

<section class="section-header">
	<div>
		<p class="section-subtitle">Core systems designed for elevated digital operations</p>
		<h2 class="section-title">Strategic domains</h2>
	</div>
</section>

<div class="feature-grid">
	<GlassCard>
		<BlueprintIcon type="cube" size={72} />
		<div class="card-label">Digital Real Estate</div>
		<h3 class="card-heading">Architectural web systems</h3>
		<p class="card-copy">Bespoke SvelteKit platforms and hybrid-rendered experiences designed for premium conversion and brand authority.</p>
	</GlassCard>

	<GlassCard>
		<BlueprintIcon type="waveform" size={72} />
		<div class="card-label">AI Orchestration</div>
		<h3 class="card-heading">Intelligent dialogue and context</h3>
		<p class="card-copy">Elegant conversational layers that feel refined, with a focus on service automation, concierge workflows, and contextual continuity.</p>
	</GlassCard>

	<GlassCard>
		<BlueprintIcon type="matrix" size={72} />
		<div class="card-label">Automation Matrix</div>
		<h3 class="card-heading">Systems that move without compromise</h3>
		<p class="card-copy">Conveyor-style process networks that synchronize bookings, guest journeys, and high-value operations across luxury ecosystems.</p>
	</GlassCard>
</div>
