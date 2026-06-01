<script lang="ts">
	import GlassCard from '$lib/components/GlassCard.svelte';
	import BlueprintIcon from '$lib/components/BlueprintIcon.svelte';
	import StatusPulse from '$lib/components/StatusPulse.svelte';
</script>

<!-- HERO SECTION: Macro-Whitespace, Editorial Framing -->
<section class="hero-section container-architect">
	<div class="hero-header-meta">
		<StatusPulse statusText="CORE POSITION: REGISTERED" size="sm" />
		<span class="technical-coord">[ ARCHITECT CODE: VYOME_001 ]</span>
	</div>

	<div class="hero-content">
		<h1 class="hero-title">
			<span class="hero-line">We Architect</span>
			<span class="hero-line line-highlight">High-End</span>
			<span class="hero-line">Digital</span>
			<span class="hero-line">Ecosystems</span>
		</h1>
		
		<div class="hero-narrative">
			<p class="narrative-body">
				For luxury resorts, elite fashion labels, premium real estate, and avant-garde architectural practices. We do not build standard software; we compose digital real estate.
			</p>
			
			<div class="hero-actions">
				<a href="/studio" class="btn-architectural">
					<span class="btn-text">Initiate Brief</span>
					<span class="btn-arrow">&rarr;</span>
				</a>
				<a href="/ecosystems" class="btn-secondary-link">
					Explore Portfolio
				</a>
			</div>
		</div>
	</div>
</section>

<!-- TECHNICAL DOMAINS SHOWCASE -->
<section class="section-spacer section-domains">
	<div class="container-architect">
		<div class="section-header">
			<span class="tech-badge">
				<span class="status-dot"></span>
				<span>01 / CAPABILITIES</span>
			</span>
			<h2 class="section-title">Core Systems</h2>
			<hr class="divider-platinum" />
		</div>

		<div class="domains-grid">
			<!-- Web Development -->
			<GlassCard padding="large" class="domain-card">
				<div class="card-icon">
					<BlueprintIcon type="cube" size={72} />
				</div>
				<div class="card-content">
					<span class="card-num">SYS.01</span>
					<h3 class="card-title">Digital Real Estate</h3>
					<p class="card-body">
						High-speed web ecosystems engineered with bespoke layouts, ultra-clean codebases, and pixel-perfect design grids matching the standards of luxury brands.
					</p>
					<ul class="card-spec-list">
						<li>[ CORE: SVELTEKIT / VITE ]</li>
						<li>[ RENDER: HYBRID STATIC/SSR ]</li>
						<li>[ LATENCY: sub-100ms TTFB ]</li>
					</ul>
				</div>
			</GlassCard>

			<!-- AI Orchestration -->
			<GlassCard padding="large" class="domain-card">
				<div class="card-icon">
					<BlueprintIcon type="waveform" size={72} />
				</div>
				<div class="card-content">
					<span class="card-num">SYS.02</span>
					<h3 class="card-title">AI Orchestration</h3>
					<p class="card-body">
						Intelligent conversational models and orbital agent cores that represent boutique customer service standards, elevating digital interactions to bespoke hospitality.
					</p>
					<ul class="card-spec-list">
						<li>[ ENGINE: Bespoke Agent Core ]</li>
						<li>[ ORBIT: Overlapping Frequency ]</li>
						<li>[ CONTEXT: Unlimited memory ]</li>
					</ul>
				</div>
			</GlassCard>

			<!-- Automation Matrix -->
			<GlassCard padding="large" class="domain-card">
				<div class="card-icon">
					<BlueprintIcon type="matrix" size={72} />
				</div>
				<div class="card-content">
					<span class="card-num">SYS.03</span>
					<h3 class="card-title">Automation Matrix</h3>
					<p class="card-body">
						Conveyor pipelines synchronizing enterprise data streams, operational CRM events, and automated booking networks without single-point failures.
					</p>
					<ul class="card-spec-list">
						<li>[ INTEGRATION: ZERO-FRICTION ]</li>
						<li>[ STATE: Automated sync ]</li>
						<li>[ PULSE: Cyber Emerald lights ]</li>
					</ul>
				</div>
			</GlassCard>
		</div>
	</div>
</section>

<!-- Luxury Clientele Focus ("The Atelier Sectors") -->
<section class="section-spacer section-sectors">
	<div class="container-architect">
		<div class="section-header">
			<span class="tech-badge">
				<span class="status-dot"></span>
				<span>02 / CLIENT CONTEXT</span>
			</span>
			<h2 class="section-title">Atelier Sectors</h2>
			<hr class="divider-platinum" />
		</div>

		<div class="sectors-grid">
			<!-- Sector 1: Luxury Resorts & Boutique Hotels -->
			<div class="sector-block">
				<div class="sector-header-row">
					<span class="sector-index">[ SECTOR.01 ]</span>
					<span class="sector-status">[ COMPILING INTEGRATIONS ]</span>
				</div>
				<h3 class="sector-title font-editorial">Luxury Resorts & Boutique Hotels</h3>
				<p class="sector-description">
					Custom digital front-ends presenting ultra-rich immersive visuals, integrated reservation APIs, and automated agent services tailored for elite international travelers.
				</p>
			</div>

			<!-- Sector 2: Luxury Fashion Brands -->
			<div class="sector-block">
				<div class="sector-header-row">
					<span class="sector-index">[ SECTOR.02 ]</span>
					<span class="sector-status">[ IMMERSIVE 3D GRIDS ]</span>
				</div>
				<h3 class="sector-title font-editorial">Luxury Fashion Brands</h3>
				<p class="sector-description">
					Couture digital cataloguing. Fast, responsive, fluid layouts focused on macro-whitespace and high-fidelity typography, preserving structural integrity.
				</p>
			</div>

			<!-- Sector 3: Premium Real Estate & Architecture -->
			<div class="sector-block">
				<div class="sector-header-row">
					<span class="sector-index">[ SECTOR.03 ]</span>
					<span class="sector-status">[ SECURE BLOCKNETS ]</span>
				</div>
				<h3 class="sector-title font-editorial">Real Estate & Architectural Firms</h3>
				<p class="sector-description">
					High-fidelity rendering viewports, digital brochures, and automated CRM linkages crafted to display premier developments with surgical aesthetic precision.
				</p>
			</div>
		</div>
	</div>
</section>

<style>
	/* Hero Section Styling */
	.hero-section {
		padding-top: clamp(80px, 12vh, 160px);
		padding-bottom: clamp(60px, 10vh, 120px);
		display: flex;
		flex-direction: column;
		gap: 60px;
	}

	.hero-header-meta {
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex-wrap: wrap;
		gap: 16px;
		border-bottom: 1px solid rgba(var(--color-accent), 0.08);
		padding-bottom: 24px;
	}

	.technical-coord {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.1em;
	}

	.hero-content {
		display: grid;
		grid-template-columns: 1.2fr 1fr;
		gap: 40px;
		align-items: start;
	}

	@media (max-width: 968px) {
		.hero-content {
			grid-template-columns: 1fr;
			gap: 40px;
		}
	}

	.hero-title {
		display: flex;
		flex-direction: column;
		font-size: clamp(3rem, 7vw, 6.5rem);
		line-height: 0.95;
		font-weight: 500;
		letter-spacing: 0.02em;
	}

	.hero-line {
		display: block;
	}

	.line-highlight {
		font-family: var(--font-editorial);
		font-style: italic;
		font-weight: 300;
		color: rgba(var(--color-text), 0.85);
		text-transform: none;
		letter-spacing: normal;
		margin-left: 0.2em;
	}

	.hero-narrative {
		display: flex;
		flex-direction: column;
		gap: clamp(24px, 4vw, 40px);
		padding-top: 16px;
	}

	.narrative-body {
		font-family: var(--font-body);
		font-size: clamp(1.1rem, 2vw, 1.35rem);
		line-height: 1.6;
		color: rgba(var(--color-text), 0.75);
		font-weight: 300;
	}

	.hero-actions {
		display: flex;
		align-items: center;
		gap: 24px;
		flex-wrap: wrap;
	}

	/* Architectural Button */
	.btn-architectural {
		display: inline-flex;
		align-items: center;
		gap: 16px;
		background-color: rgb(var(--color-text));
		color: rgb(var(--color-bg));
		text-decoration: none;
		padding: 14px 28px;
		font-family: var(--font-mono);
		font-size: 12px;
		letter-spacing: 0.15em;
		text-transform: uppercase;
		font-weight: 500;
		transition: background-color var(--transition-medium), transform var(--transition-medium);
	}

	.btn-architectural:hover {
		background-color: rgb(var(--color-accent-hex));
		transform: translateY(-1px);
	}

	.btn-arrow {
		transition: transform var(--transition-medium);
	}

	.btn-architectural:hover .btn-arrow {
		transform: translateX(4px);
	}

	.btn-secondary-link {
		font-family: var(--font-mono);
		font-size: 12px;
		letter-spacing: 0.15em;
		text-transform: uppercase;
		color: rgba(var(--color-text), 0.7);
		text-decoration: none;
		border-bottom: 1px solid rgba(var(--color-accent), 0.2);
		padding-bottom: 4px;
		transition: color var(--transition-medium), border-color var(--transition-medium);
	}

	.btn-secondary-link:hover {
		color: rgb(var(--color-text));
		border-color: rgb(var(--color-text));
	}

	/* Domain section */
	.section-header {
		margin-bottom: clamp(40px, 8vw, 80px);
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 16px;
	}

	.section-title {
		font-size: clamp(2rem, 4vw, 3rem);
		letter-spacing: 0.15em;
		color: rgb(var(--color-text));
	}

	.domains-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: clamp(20px, 3vw, 40px);
	}

	@media (max-width: 1024px) {
		.domains-grid {
			grid-template-columns: 1fr;
			gap: 30px;
		}
	}

	:global(.domain-card) {
		display: flex;
		flex-direction: column;
		gap: 32px;
		height: 100%;
	}

	.card-num {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.12em;
		margin-bottom: 8px;
		display: block;
	}

	.card-title {
		font-size: clamp(1.2rem, 2vw, 1.5rem);
		margin-bottom: 16px;
		letter-spacing: 0.1em;
	}

	.card-body {
		font-size: 0.95rem;
		line-height: 1.6;
		color: rgba(var(--color-text), 0.65);
		margin-bottom: 24px;
	}

	.card-spec-list {
		list-style: none;
		border-top: 1px solid rgba(var(--color-accent), 0.08);
		padding-top: 20px;
		display: flex;
		flex-direction: column;
		gap: 8px;
	}

	.card-spec-list li {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.5);
		letter-spacing: 0.1em;
	}

	/* Sectors section */
	.sectors-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: clamp(40px, 6vw, 80px);
	}

	@media (max-width: 1024px) {
		.sectors-grid {
			grid-template-columns: 1fr;
			gap: 50px;
		}
	}

	.sector-block {
		display: flex;
		flex-direction: column;
		gap: 20px;
		border-left: 1px solid rgba(var(--color-accent), 0.1);
		padding-left: 24px;
		transition: border-color var(--transition-medium);
	}

	.sector-block:hover {
		border-color: rgba(var(--color-accent), 0.4);
	}

	.sector-header-row {
		display: flex;
		justify-content: space-between;
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.1em;
	}

	.sector-title {
		font-size: clamp(1.4rem, 2.5vw, 2.1rem);
		text-transform: none;
		letter-spacing: normal;
		line-height: 1.2;
	}

	.sector-description {
		font-size: 0.95rem;
		line-height: 1.6;
		color: rgba(var(--color-text), 0.6);
	}
</style>
