<script lang="ts">
import GlassCard from '$lib/components/GlassCard.svelte';
import StatusPulse from '$lib/components/StatusPulse.svelte';
</script>

<section class="section-header">
	<div>
		<p class="section-subtitle">Foundational systems, compositional workflows, and service design</p>
		<h2 class="section-title">Services</h2>
	</div>
</section>

<div class="service-grid">
	<GlassCard>
		<StatusPulse statusText="SYSTEM STATUS: STRATEGY" />
		<div class="card-label">Digital Strategy</div>
		<h3 class="card-heading">Architectural planning</h3>
		<p class="card-copy">From brand scaffolding to technical operations, we define luxe digital systems that support long-term premium experiences.</p>
	</GlassCard>

	<GlassCard>
		<StatusPulse statusText="SYSTEM STATUS: BUILD" />
		<div class="card-label">Design & Build</div>
		<h3 class="card-heading">Bespoke platform creation</h3>
		<p class="card-copy">SvelteKit deployments, glassmorphic interface systems, and polished workflows built for editorial density and quiet luxury.</p>
	</GlassCard>

	<GlassCard>
		<StatusPulse statusText="SYSTEM STATUS: AUTOMATION" />
		<div class="card-label">Orchestration</div>
		<h3 class="card-heading">Automation & AI</h3>
		<p class="card-copy">Smooth, cinematic process flows and concierge automation that create premium sustainable systems for modern enterprises.</p>
	</GlassCard>
</div>
