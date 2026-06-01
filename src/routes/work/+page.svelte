<script lang="ts">
import GlassCard from '$lib/components/GlassCard.svelte';
import BlueprintIcon from '$lib/components/BlueprintIcon.svelte';
</script>

<section class="section-header">
	<div>
		<p class="section-subtitle">Selected creative systems with elevated architecture</p>
		<h2 class="section-title">Work</h2>
	</div>
</section>

<div class="case-grid">
	<GlassCard>
		<div class="status-badge"><span class="status-dot"></span>Luxury Resort Platform</div>
		<h3 class="card-heading">Immersive hospitality ecosystems</h3>
		<p class="card-copy">High-fidelity reservation flows, rich editorial interiors, and context-aware automation tailored for a global luxury hospitality brand.</p>
		<ul class="card-list">
			<li>[ HYBRID RENDERING ]</li>
			<li>[ DYNAMIC LIVE AVAILABILITY ]</li>
			<li>[ CONCIERGE AI ]</li>
		</ul>
	</GlassCard>

	<GlassCard>
		<div class="status-badge"><span class="status-dot"></span>Fashion Intelligence</div>
		<h3 class="card-heading">Editorial commerce systems</h3>
		<p class="card-copy">Minimal interface systems that feel custom-made, with precision routing, imagery-first storytelling, and boutique product architecture.</p>
		<ul class="card-list">
			<li>[ CURATED CONTENT ]</li>
			<li>[ BESPOKE INTERFACES ]</li>
			<li>[ SOFT MOTION ]</li>
		</ul>
	</GlassCard>

	<GlassCard>
		<div class="status-badge"><span class="status-dot"></span>Architectural Digital Brochures</div>
		<h3 class="card-heading">Real estate and studio narratives</h3>
		<p class="card-copy">Quiet frames for bold portfolio work, structured around spatial clarity, elevated typography, and performance-first loading.</p>
		<ul class="card-list">
			<li>[ STRATEGIC PROPOSALS ]</li>
			<li>[ IMMERSIVE STORYLINES ]</li>
			<li>[ FAST LOADING ]</li>
		</ul>
	</GlassCard>
</div>
