<script lang="ts">
	import GlassCard from '$lib/components/GlassCard.svelte';
	import StatusPulse from '$lib/components/StatusPulse.svelte';
</script>

<svelte:head>
	<title>VYOME | The Master Architects & Digital Methodology</title>
	<meta name="description" content="Explore Vyome's architectural digital transformation methodology. We compile digital legacy using bespoke layouts, JSDoc annotations, and automated execution cores." />
</svelte:head>

<!-- METHODOLOGY HERO -->
<section class="architects-hero container-architect">
	<div class="header-meta">
		<StatusPulse statusText="METHODOLOGY: ENCRYPTED" size="sm" />
		<span class="technical-ver">[ GRID SYSTEM: RESOLVED ]</span>
	</div>

	<div class="hero-title-block">
		<h1 class="architects-title">Master Architects</h1>
		<p class="architects-subtitle">
			We do not code; we architect premium digital real estate. Discover our core blueprint methodology, balancing absolute luxury aesthetic standards with highly-optimized technical execution.
		</p>
	</div>
</section>

<!-- THE THREE-PHASE BLUEPRINT -->
<section class="section-spacer container-architect blueprint-phases">
	<div class="phases-grid">
		<!-- Phase 1 -->
		<div class="phase-column">
			<div class="phase-meta">
				<span class="tech-badge">[ PHASE.01 / AESTHETICS ]</span>
				<span class="phase-number">01</span>
			</div>
			
			<h3 class="phase-title font-editorial">Couture Digital Drafting</h3>
			
			<p class="phase-body">
				Every project begins with absolute visual curation. We reject standardized layout systems and generic tech agency templates. We frame luxury assets within generous macro-whitespace, utilizing curated, high-end editorial typography like Cormorant Garamond and Clash Display to enforce high brand status.
			</p>
			
			<ul class="phase-specs">
				<li>[ DENSITY: 20% INFODENSITY ]</li>
				<li>[ ALIGNMENT: CUSTOM ASSET GRIDS ]</li>
				<li>[ GRAPHICS: MONOCHROMATIC VECTORS ]</li>
			</ul>
		</div>

		<!-- Phase 2 -->
		<div class="phase-column border-col">
			<div class="phase-meta">
				<span class="tech-badge">[ PHASE.02 / SYSTEM CORE ]</span>
				<span class="phase-number">02</span>
			</div>
			
			<h3 class="phase-title font-editorial">High-Fidelity Engineering</h3>
			
			<p class="phase-body">
				The core architecture is scaffolded in SvelteKit and Vite. Our code is written to absolute standards of efficiency, structured with complete TypeScript safety and JSDoc annotations. We achieve near-instantaneous load times through static edge caching and hybrid rendering solutions.
			</p>
			
			<ul class="phase-specs">
				<li>[ RENDER: EDGE HYBRID SSR ]</li>
				<li>[ PERFORMANCE: 100 LIGHTHOUSE ]</li>
				<li>[ COMPILER: STRICT TYPESCRIPT ]</li>
			</ul>
		</div>

		<!-- Phase 3 -->
		<div class="phase-column border-col">
			<div class="phase-meta">
				<span class="tech-badge">[ PHASE.03 / AUTOMATION ]</span>
				<span class="phase-number">03</span>
			</div>
			
			<h3 class="phase-title font-editorial">Autonomous Conveyance</h3>
			
			<p class="phase-body">
				We orchestrate fully automated digital ecosystems. Our custom AI agent systems represent elite boutique concierge services, while our integration matrices synchronize booking engines, real estate portals, and corporate ERP databases without single points of failure.
			</p>
			
			<ul class="phase-specs">
				<li>[ INTEGRATION: CRM/ERP NETWORKS ]</li>
				<li>[ AGENT: ORBITAL FREQUENCY AI ]</li>
				<li>[ MONITORING: CYBER EMERALD PULSES ]</li>
			</ul>
		</div>
	</div>
</section>

<!-- ARCHITECTURAL CODE STANDARDS SHOWCASE -->
<section class="section-spacer container-architect code-showcase-section">
	<div class="section-header">
		<span class="tech-badge">
			<span class="status-dot"></span>
			<span>03 / TECHNICAL SPECIFICATION</span>
		</span>
		<h2 class="section-title">The Code Blueprint</h2>
		<hr class="divider-platinum" />
	</div>

	<div class="showcase-content">
		<div class="showcase-description">
			<p class="editorial-text font-editorial">
				"True luxury is reflected in what is unseen."
			</p>
			<p class="narrative-body">
				Just as the foundation of an architectural masterpiece dictates its longevity, the quality of our code dictates your digital stability. We present our standard interface blueprint for automated luxury hospitality reserving, showcasing our commitment to high-end engineering.
			</p>
			
			<div class="tech-metrics">
				<div class="metric-box">
					<span class="metric-title">[ STACK ]</span>
					<span class="metric-val">TypeScript</span>
				</div>
				<div class="metric-box">
					<span class="metric-title">[ COMPILER ]</span>
					<span class="metric-val">Strict V5</span>
				</div>
				<div class="metric-box">
					<span class="metric-title">[ STAT ]</span>
					<span class="metric-val" style="color: rgb(var(--color-pulse));">PASSING</span>
				</div>
			</div>
		</div>

		<!-- Code Display GlassCard -->
		<GlassCard padding="large" class="code-editor-card" hoverEffect={false}>
			<div class="editor-header">
				<div class="window-dots">
					<span class="dot-red"></span>
					<span class="dot-yellow"></span>
					<span class="dot-green"></span>
				</div>
				<span class="editor-filename">src/lib/server/architect.ts</span>
				<span class="tech-badge">[ READ-ONLY ]</span>
			</div>
			
			<pre class="code-viewport"><code><span class="code-comment">/**
 * @file architect.ts
 * @namespace Vyome.Core.Architect
 * @description Coordinates automated reserving sequences for elite hospitality properties.
 * [ STATUS: AUTOMATED ] [ COMPILATION: SUCCESSFUL ]
 */</span>

<span class="code-keyword">import</span> &#123; EdgeOrchestrator &#125; <span class="code-keyword">from</span> <span class="code-string">'$lib/server/orchestrator'</span>;
<span class="code-keyword">import</span> type &#123; LuxuryResortEcosystem &#125; <span class="code-keyword">from</span> <span class="code-string">'$lib/types/luxury'</span>;

<span class="code-comment">/**
 * Class representing the core System Architect.
 * Implements strict latency limitations and edge rendering profiles.
 */</span>
<span class="code-keyword">export class</span> SystemArchitect &#123;
  <span class="code-keyword">private</span> orchestrator: EdgeOrchestrator;

  <span class="code-keyword">constructor</span>(ecosystem: LuxuryResortEcosystem) &#123;
    <span class="code-keyword">this</span>.orchestrator = <span class="code-keyword">new</span> EdgeOrchestrator(&#123;
      id: ecosystem.id,
      latencyBoundMs: <span class="code-number">100</span>,
      indicatorPulse: <span class="code-string">'#00E575'</span> <span class="code-comment">/* Cyber Emerald */</span>
    &#125;);
  &#125;

  <span class="code-comment">/**
   * Triggers an automated, encrypted reservation event across global PMS nodes.
   * @param clientSignature - Encrypted cryptographic customer identifier.
   */</span>
  <span class="code-keyword">public async</span> synchronizeEcosystem(clientSignature: <span class="code-keyword">string</span>): <span class="code-keyword">Promise</span>&lt;<span class="code-keyword">boolean</span>&gt; &#123;
    <span class="code-keyword">const</span> secureTunnel = <span class="code-keyword">await</span> <span class="code-keyword">this</span>.orchestrator.establishSecureTunnel(clientSignature);
    
    <span class="code-keyword">if</span> (!secureTunnel.isActive) &#123;
      <span class="code-keyword">throw new</span> Error(<span class="code-string">'[CRITICAL] Security tunnel alignment failure.'</span>);
    &#125;

    <span class="code-keyword">return await</span> <span class="code-keyword">this</span>.orchestrator.dispatchConveyorMatrix();
  &#125;
&#125;</code></pre>
		</GlassCard>
	</div>
</section>

<style>
	.architects-hero {
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

	.architects-title {
		font-size: clamp(2.5rem, 6vw, 4.5rem);
		line-height: 1.05;
	}

	.architects-subtitle {
		font-size: clamp(1.1rem, 2vw, 1.25rem);
		line-height: 1.6;
		color: rgba(var(--color-text), 0.7);
		font-weight: 300;
	}

	/* Three Phase Blueprint */
	.phases-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 40px;
	}

	@media (max-width: 1024px) {
		.phases-grid {
			grid-template-columns: 1fr;
			gap: 60px;
		}
	}

	.phase-column {
		display: flex;
		flex-direction: column;
		gap: 24px;
	}

	.border-col {
		border-left: 1px solid rgba(var(--color-accent), 0.1);
		padding-left: 40px;
	}

	@media (max-width: 1024px) {
		.border-col {
			border-left: none;
			padding-left: 0;
			border-top: 1px solid rgba(var(--color-accent), 0.1);
			padding-top: 40px;
		}
	}

	.phase-meta {
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.phase-number {
		font-family: var(--font-primary);
		font-size: 1.5rem;
		color: rgba(var(--color-accent), 0.25);
	}

	.phase-title {
		font-size: clamp(1.4rem, 2.5vw, 2rem);
		text-transform: none;
		letter-spacing: normal;
		line-height: 1.2;
		color: rgb(var(--color-text));
	}

	.phase-body {
		font-size: 0.95rem;
		line-height: 1.7;
		color: rgba(var(--color-text), 0.65);
		font-weight: 300;
	}

	.phase-specs {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 8px;
		border-top: 1px solid rgba(var(--color-accent), 0.08);
		padding-top: 20px;
	}

	.phase-specs li {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.45);
		letter-spacing: 0.1em;
	}

	/* Code Showcase Section */
	.showcase-content {
		display: grid;
		grid-template-columns: 1fr 1.3fr;
		gap: 60px;
		align-items: start;
	}

	@media (max-width: 1124px) {
		.showcase-content {
			grid-template-columns: 1fr;
			gap: 40px;
		}
	}

	.showcase-description {
		display: flex;
		flex-direction: column;
		gap: 32px;
	}

	.editorial-text {
		font-size: clamp(1.4rem, 2.5vw, 1.8rem);
		border-left: 2px solid rgba(var(--color-accent), 0.15);
		padding-left: 24px;
		line-height: 1.4;
	}

	.narrative-body {
		font-size: 1.05rem;
		line-height: 1.6;
		color: rgba(var(--color-text), 0.65);
		font-weight: 300;
	}

	.tech-metrics {
		display: flex;
		gap: clamp(16px, 3vw, 40px);
	}

	.metric-box {
		display: flex;
		flex-direction: column;
		gap: 6px;
	}

	.metric-title {
		font-family: var(--font-mono);
		font-size: 10px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.1em;
	}

	.metric-val {
		font-family: var(--font-mono);
		font-size: 13px;
		color: rgba(var(--color-text), 0.9);
		letter-spacing: 0.05em;
	}

	/* Code Editor styling */
	:global(.code-editor-card) {
		background-color: rgba(6, 6, 7, 0.95);
		border: 1px solid rgba(255, 255, 255, 0.03);
	}

	.editor-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		border-bottom: 1px solid rgba(255, 255, 255, 0.05);
		padding-bottom: 16px;
		margin-bottom: 24px;
	}

	.window-dots {
		display: flex;
		gap: 6px;
	}

	.window-dots span {
		width: 8px;
		height: 8px;
		border-radius: 50%;
		display: inline-block;
	}

	.dot-red { background-color: rgba(255, 95, 87, 0.35); }
	.dot-yellow { background-color: rgba(255, 189, 46, 0.35); }
	.dot-green { background-color: rgba(39, 201, 63, 0.35); }

	.editor-filename {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.55);
		letter-spacing: 0.05em;
	}

	.code-viewport {
		overflow-x: auto;
		font-family: var(--font-mono);
		font-size: clamp(11px, 1.8vw, 13px);
		line-height: 1.6;
		color: #e4e4e7;
		background: none;
		border: none;
		padding: 0;
	}

	/* Code Highlighting Styles */
	.code-comment { color: #71717a; font-style: italic; }
	.code-keyword { color: #a5b4fc; }
	.code-string { color: #86efac; }
	.code-number { color: #fdba74; }
</style>
