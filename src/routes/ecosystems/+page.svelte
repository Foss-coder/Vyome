<script lang="ts">
	import GlassCard from '$lib/components/GlassCard.svelte';
	import StatusPulse from '$lib/components/StatusPulse.svelte';

	const projects = [
		{
			id: 'ECO.01',
			title: 'Aman Resorts Digital Core',
			sector: 'Luxury Hospitality',
			desc: 'A unified global booking core synchronizing over 30 luxury properties worldwide. Features sub-100ms server response times, high-fidelity responsive photography grids, and automated regional concierge pipelines.',
			specs: [
				{ key: 'STACK', val: 'SvelteKit / Node.js' },
				{ key: 'LATENCY', val: '72ms TTFB Avg' },
				{ key: 'INTEGRATIONS', val: 'Synxis / Opera PMS' },
				{ key: 'SECURITY', val: 'PCI-DSS Level 1' }
			],
			status: 'OPERATIONAL',
			year: '2025'
		},
		{
			id: 'ECO.02',
			title: 'Valeska Couture Atelier',
			sector: 'Luxury Fashion',
			desc: 'An immersive digital atelier showcasing seasonal collections through 3D wireframe canvases and glassmorphic detail panels. Engineered with zero layout shifts, fluid tactile transitions, and secure checkout matrices.',
			specs: [
				{ key: 'STACK', val: 'SvelteKit / WebGL / Vite' },
				{ key: 'ANIMATION', val: 'Line-Tracing / Custom physics' },
				{ key: 'PERFORMANCE', val: '100/100 Lighthouse' },
				{ key: 'HOSTING', val: 'Distributed Edge' }
			],
			status: 'OPERATIONAL',
			year: '2026'
		},
		{
			id: 'ECO.03',
			title: 'The Obsidian Tower Portal',
			sector: 'Premium Real Estate',
			desc: 'A private transaction and rendering viewport for a premier architectural landmark in Zurich. Integrates real-time structural asset streams, encrypted smart contract ledgers, and boutique client dashboards.',
			specs: [
				{ key: 'STACK', val: 'SvelteKit / Tailwind / Rust' },
				{ key: 'INTEGRATIONS', val: 'Salesforce CRM / DocuSign' },
				{ key: 'SECURITY', val: 'AES-256 Private Portal' },
				{ key: 'DEVICES', val: 'Strictly multi-device fluid' }
			],
			status: 'OPERATIONAL',
			year: '2026'
		},
		{
			id: 'ECO.04',
			title: 'Atelier Khora Portfolio',
			sector: 'Architecture Practice',
			desc: 'A sparse, highly editorial portfolio web presence designed to showcase award-winning projects with maximum macro-whitespace. Built with a custom blueprint grid system and smooth page transitions.',
			specs: [
				{ key: 'STACK', val: 'SvelteKit / CSS Custom Grid' },
				{ key: 'TYPOGRAPHY', val: 'Clash Display / Satoshi' },
				{ key: 'DENSITY', val: 'Intentionally low (80/20)' },
				{ key: 'COMPAT', val: 'Fluid responsive vector canvas' }
			],
			status: 'STANDBY',
			year: '2025'
		}
	];
</script>

<svelte:head>
	<title>VYOME | Luxury Digital Ecosystems Portfolio</title>
	<meta name="description" content="Explore Vyome's portfolio of luxury digital architectures, high-performance web systems, and custom AI ecosystems engineered for elite sectors." />
</svelte:head>

<!-- PORTFOLIO HEADER -->
<section class="portfolio-hero container-architect">
	<div class="header-meta">
		<StatusPulse statusText="PORTFOLIO STREAMS: VERIFIED" size="sm" />
		<span class="technical-ver">[ CLIENT DATA PRESERVED ]</span>
	</div>

	<div class="hero-title-block">
		<h1 class="portfolio-title">Flagship Ecosystems</h1>
		<p class="portfolio-subtitle">
			A curated chronicle of architectural transformations. We elevate digital codebases into high-end real estate, blending surgical technical precision with absolute aesthetic focus.
		</p>
	</div>
</section>

<!-- PROJECTS GRID -->
<section class="section-spacer projects-section">
	<div class="container-architect">
		<div class="projects-grid">
			{#each projects as project}
				<GlassCard padding="large" class="project-card">
					<div class="project-header">
						<span class="project-id">{project.id}</span>
						<span class="project-year">// {project.year}</span>
					</div>

					<div class="project-body">
						<span class="tech-badge sector-tag">
							<span class="status-dot" style="background-color: {project.status === 'OPERATIONAL' ? 'rgb(var(--color-pulse))' : 'rgba(var(--color-accent), 0.4)'}; box-shadow: {project.status === 'OPERATIONAL' ? '0 0 6px rgb(var(--color-pulse))' : 'none'};"></span>
							<span>{project.sector}</span>
						</span>
						
						<h2 class="project-title font-editorial">{project.title}</h2>
						<p class="project-desc">{project.desc}</p>
					</div>

					<div class="project-footer">
						<div class="specs-grid">
							{#each project.specs as spec}
								<div class="spec-row">
									<span class="spec-key">{spec.key}:</span>
									<span class="spec-val">{spec.val}</span>
								</div>
							{/each}
						</div>
						
						<div class="project-action-row">
							<span class="status-indicator">
								[ STATUS: <span class="status-highlight" class:pulse={project.status === 'OPERATIONAL'}>{project.status}</span> ]
							</span>
						</div>
					</div>
				</GlassCard>
			{/each}
		</div>
	</div>
</section>

<!-- CALL TO ACTION -->
<section class="section-spacer portfolio-cta">
	<div class="container-architect">
		<GlassCard padding="large" class="cta-card">
			<div class="cta-content">
				<h2 class="cta-title">Ready to Architect Your Ecosystem?</h2>
				<p class="cta-body">
					Enter our interactive studio to configure your digital atelier brief and establish direct contact with our master engineers.
				</p>
				<a href="/studio" class="btn-architectural">
					<span>Enter Studio Workspace</span>
					<span>&rarr;</span>
				</a>
			</div>
		</GlassCard>
	</div>
</section>

<style>
	.portfolio-hero {
		padding-top: clamp(60px, 10vh, 120px);
		border-bottom: 1px solid rgba(var(--color-accent), 0.08);
		padding-bottom: 40px;
	}

	.header-meta {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 40px;
	}

	.technical-ver {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.12em;
	}

	.hero-title-block {
		max-width: 800px;
		display: flex;
		flex-direction: column;
		gap: 20px;
	}

	.portfolio-title {
		font-size: clamp(2.5rem, 6vw, 4.5rem);
		line-height: 1.05;
	}

	.portfolio-subtitle {
		font-size: clamp(1.1rem, 2vw, 1.25rem);
		line-height: 1.6;
		color: rgba(var(--color-text), 0.7);
		font-weight: 300;
	}

	/* Projects Grid */
	.projects-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: clamp(24px, 4vw, 48px);
	}

	@media (max-width: 1024px) {
		.projects-grid {
			grid-template-columns: 1fr;
			gap: 40px;
		}
	}

	:global(.project-card) {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		gap: 40px;
		height: 100%;
	}

	.project-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.1em;
	}

	.project-body {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 20px;
	}

	.sector-tag {
		margin-bottom: 4px;
	}

	.project-title {
		font-size: clamp(1.6rem, 3vw, 2.4rem);
		text-transform: none;
		letter-spacing: normal;
		line-height: 1.15;
		color: rgb(var(--color-text));
	}

	.project-desc {
		font-size: 0.95rem;
		line-height: 1.7;
		color: rgba(var(--color-text), 0.65);
	}

	.project-footer {
		border-top: 1px solid rgba(var(--color-accent), 0.08);
		padding-top: 24px;
		display: flex;
		flex-direction: column;
		gap: 20px;
	}

	.specs-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 12px;
	}

	@media (max-width: 480px) {
		.specs-grid {
			grid-template-columns: 1fr;
		}
	}

	.spec-row {
		display: flex;
		gap: 8px;
		font-family: var(--font-mono);
		font-size: 11px;
		letter-spacing: 0.05em;
	}

	.spec-key {
		color: rgba(var(--color-accent), 0.45);
	}

	.spec-val {
		color: rgba(var(--color-text), 0.8);
	}

	.project-action-row {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.status-indicator {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.45);
		letter-spacing: 0.1em;
	}

	.status-highlight {
		color: rgba(var(--color-accent), 0.7);
	}

	.status-highlight.pulse {
		color: rgb(var(--color-pulse));
		text-shadow: 0 0 8px rgba(var(--color-pulse), 0.3);
	}

	/* Call to Action card */
	:global(.cta-card) {
		background: linear-gradient(135deg, rgba(var(--color-bg), 0.9) 0%, rgba(var(--color-accent), 0.02) 100%);
		text-align: center;
	}

	.cta-content {
		max-width: 600px;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 24px;
	}

	.cta-title {
		font-size: clamp(1.8rem, 4vw, 2.8rem);
		letter-spacing: 0.05em;
		line-height: 1.15;
	}

	.cta-body {
		font-size: 1rem;
		line-height: 1.6;
		color: rgba(var(--color-text), 0.65);
		margin-bottom: 8px;
	}
</style>
