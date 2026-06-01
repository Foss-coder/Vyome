<script lang="ts">
	import GlassCard from '$lib/components/GlassCard.svelte';
	import StatusPulse from '$lib/components/StatusPulse.svelte';

	// Client Onboarding Reactive State (Svelte 5)
	let clientName = $state('');
	let orgName = $state('');
	let email = $state('');
	let selectedSector = $state('Luxury Hospitality');
	let selectedScale = $state('Full Digital Atelier');
	let aestheticWeight = $state(20); // 80/20 default whitespace slider

	let isSubmitting = $state(false);
	let isSubmitted = $state(false);
	let clientHash = $state('');

	const sectors = [
		'Luxury Hospitality',
		'High Fashion',
		'Real Estate / Architecture',
		'Custom Luxury Sector'
	];

	const scales = [
		{ label: 'Bbespoke Web Portal', time: '8-10 weeks', code: 'SYS.01' },
		{ label: 'AI Concierge Core', time: '6-8 weeks', code: 'SYS.02' },
		{ label: 'Operational Sync Matrix', time: '10-12 weeks', code: 'SYS.03' },
		{ label: 'Full Digital Atelier', time: '14-16 weeks', code: 'SYS.ALL' }
	];

	function handleSubmit(e: SubmitEvent) {
		e.preventDefault();
		if (!clientName || !email) return;

		isSubmitting = true;

		// Generate random architectural hash
		const randomChars = Math.random().toString(36).substring(2, 10).toUpperCase();
		clientHash = `VYM_${selectedSector.substring(0, 3).toUpperCase()}_${randomChars}`;

		setTimeout(() => {
			isSubmitting = false;
			isSubmitted = true;
		}, 2000);
	}

	function resetForm() {
		clientName = '';
		orgName = '';
		email = '';
		isSubmitted = false;
		clientHash = '';
	}

	// Dynamic estimated complexity based on scale
	let computedTime = $derived(
		scales.find(s => s.label === selectedScale)?.time || 'TBD'
	);
	
	let computedCode = $derived(
		scales.find(s => s.label === selectedScale)?.code || 'SYS.TBD'
	);
</script>

<svelte:head>
	<title>VYOME | Atelier Studio Client Briefing Portal</title>
	<meta name="description" content="Initiate your high-end digital ecosystem brief in Vyome's interactive atelier workspace. Select your market sector, scaling, and aesthetic direction." />
</svelte:head>

<!-- STUDIO HERO -->
<section class="studio-hero container-architect">
	<div class="header-meta">
		<StatusPulse statusText={isSubmitted ? "COMPILATION: SUCCESS" : "ATELIER STATE: READY"} size="sm" />
		<span class="technical-ver">[ REGISTRATION: OPEN ]</span>
	</div>

	<div class="hero-title-block">
		<h1 class="studio-title">Atelier Studio</h1>
		<p class="studio-subtitle">
			Configure your digital transformation brief. Select your parameters, define your brand aesthetic density, and compile your ecosystem architecture request directly into our engineers' queue.
		</p>
	</div>
</section>

<!-- INTERACTIVE WIZARD GRID -->
<section class="section-spacer container-architect briefing-workspace">
	{#if !isSubmitted}
		<div class="workspace-grid">
			<!-- Form Column -->
			<GlassCard padding="large" class="form-container-card" hoverEffect={false}>
				<form onsubmit={handleSubmit} class="onboarding-form">
					<div class="form-section-header">
						<span class="tech-badge">[ SECTION 01 / IDENTIFICATION ]</span>
					</div>

					<div class="input-group">
						<label for="clientName" class="form-label">Client Name *</label>
						<input 
							type="text" 
							id="clientName" 
							bind:value={clientName} 
							placeholder="e.g. AMAN RESORTS DIRECTORY"
							class="text-input" 
							required 
						/>
					</div>

					<div class="input-group">
						<label for="orgName" class="form-label">Organization Name</label>
						<input 
							type="text" 
							id="orgName" 
							bind:value={orgName} 
							placeholder="e.g. AMAN RESORT GROUP"
							class="text-input" 
						/>
					</div>

					<div class="input-group">
						<label for="email" class="form-label">Secure Contact Email *</label>
						<input 
							type="email" 
							id="email" 
							bind:value={email} 
							placeholder="e.g. communications@aman.com"
							class="text-input" 
							required 
						/>
					</div>

					<div class="form-section-header">
						<span class="tech-badge">[ SECTION 02 / ECOSYSTEM PROFILE ]</span>
					</div>

					<div class="input-group">
						<span class="form-label">Market Sector</span>
						<div class="options-grid">
							{#each sectors as sector}
								<button 
									type="button" 
									class="option-selector" 
									class:selected={selectedSector === sector}
									onclick={() => selectedSector = sector}
								>
									{sector}
								</button>
							{/each}
						</div>
					</div>

					<div class="input-group">
						<span class="form-label">System Scaling Cores</span>
						<div class="options-grid">
							{#each scales as scale}
								<button 
									type="button" 
									class="option-selector" 
									class:selected={selectedScale === scale.label}
									onclick={() => selectedScale = scale.label}
								>
									<span class="option-code">{scale.code}</span>
									<span class="option-label">{scale.label}</span>
								</button>
							{/each}
						</div>
					</div>

					<div class="input-group">
						<div class="slider-header">
							<span class="form-label">Aesthetic WhiteSpace Density</span>
							<span class="slider-value">[ {100 - aestheticWeight}% / {aestheticWeight}% ]</span>
						</div>
						<input 
							type="range" 
							min="10" 
							max="50" 
							bind:value={aestheticWeight} 
							class="range-slider"
						/>
						<div class="slider-labels">
							<span>Ultra Sparse Editorial (Luxury)</span>
							<span>Dense Blueprint Grid (Tech)</span>
						</div>
					</div>

					<button 
						type="submit" 
						class="btn-architectural btn-submit"
						disabled={isSubmitting}
					>
						<span>{isSubmitting ? 'COMPILING BRIEF...' : 'COMPILE AND DEPLOY BRIEF'}</span>
						<span>&rarr;</span>
					</button>
				</form>
			</GlassCard>

			<!-- Dynamic Receipt Column -->
			<div class="receipt-container">
				<GlassCard padding="large" class="receipt-card" hoverEffect={false}>
					<div class="receipt-header">
						<StatusPulse statusText={isSubmitting ? "COMPILING SYSTEM" : "ATELIER STANDBY"} size="sm" />
						<span class="receipt-logo">VYOME ARCH.</span>
					</div>

					<hr class="divider-dashed" />

					<div class="receipt-specs">
						<h3 class="receipt-title font-editorial">Blueprint Specimen</h3>
						
						<div class="receipt-row">
							<span class="r-key">SYSTEM SCALE:</span>
							<span class="r-val">{selectedScale}</span>
						</div>
						<div class="receipt-row">
							<span class="r-key">TARGET SECTOR:</span>
							<span class="r-val">{selectedSector}</span>
						</div>
						<div class="receipt-row">
							<span class="r-key">GRID RATIO:</span>
							<span class="r-val">{100 - aestheticWeight}/{aestheticWeight} (WHITESPACE)</span>
						</div>
						<div class="receipt-row">
							<span class="r-key">SYSTEM CODE:</span>
							<span class="r-val" style="color: rgb(var(--color-pulse));">{computedCode}</span>
						</div>
						
						<hr class="divider-dashed" />

						<div class="receipt-row">
							<span class="r-key">CLIENT ORG:</span>
							<span class="r-val">{orgName || '[ TBD ]'}</span>
						</div>
						<div class="receipt-row">
							<span class="r-key">ESTIMATED TIMELINE:</span>
							<span class="r-val">{computedTime}</span>
						</div>
						<div class="receipt-row">
							<span class="r-key">ENCRYPTION PORT:</span>
							<span class="r-val">SECURE_SSL</span>
						</div>
					</div>

					<div class="receipt-footer">
						<span class="technical-hash">[ HASH: PENDING COMPILATION ]</span>
					</div>
				</GlassCard>
			</div>
		</div>
	{:else}
		<!-- Submission Success GlassCard -->
		<GlassCard padding="large" class="success-matrix-card" hoverEffect={false}>
			<div class="success-header">
				<div class="success-glowing-circle">
					<StatusPulse showText={false} size="md" />
				</div>
				
				<span class="tech-badge success-badge">[ COMPILATION SUCCESSFUL ]</span>
			</div>

			<div class="success-body">
				<h2 class="success-title font-editorial">Atelier Brief Registered</h2>
				<p class="success-message">
					We have successfully compiled and scheduled your digital ecosystem briefing matrix. Our chief systems engineers will review your layout parameters and establish a secure alignment portal within 24 operational hours.
				</p>

				<div class="success-blueprint-receipt">
					<div class="s-row">
						<span class="s-label">CLIENT CODENAME:</span>
						<span class="s-info">{clientName.toUpperCase()}</span>
					</div>
					<div class="s-row">
						<span class="s-label">CRYPTOGRAPHIC SIGNATURE:</span>
						<span class="s-info font-mono-highlight">{clientHash}</span>
					</div>
					<div class="s-row">
						<span class="s-label">ESTIMATED LAUNCH MATRIX:</span>
						<span class="s-info">{computedTime}</span>
					</div>
					<div class="s-row">
						<span class="s-label">SECURE CORRESPONDENCE:</span>
						<span class="s-info">{email}</span>
					</div>
				</div>

				<button onclick={resetForm} class="btn-architectural btn-success-back">
					<span>Register New Brief</span>
				</button>
			</div>
		</GlassCard>
	{/if}
</section>

<style>
	.studio-hero {
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

	.studio-title {
		font-size: clamp(2.5rem, 6vw, 4.5rem);
		line-height: 1.05;
	}

	.studio-subtitle {
		font-size: clamp(1.1rem, 2vw, 1.25rem);
		line-height: 1.6;
		color: rgba(var(--color-text), 0.7);
		font-weight: 300;
	}

	/* Briefing Workspace layout */
	.workspace-grid {
		display: grid;
		grid-template-columns: 1.5fr 1fr;
		gap: 40px;
		align-items: start;
	}

	@media (max-width: 1024px) {
		.workspace-grid {
			grid-template-columns: 1fr;
			gap: 40px;
		}
	}

	.onboarding-form {
		display: flex;
		flex-direction: column;
		gap: clamp(24px, 4vw, 36px);
	}

	.form-section-header {
		border-bottom: 1px solid rgba(var(--color-accent), 0.08);
		padding-bottom: 12px;
		margin-top: 10px;
	}

	.input-group {
		display: flex;
		flex-direction: column;
		gap: 10px;
	}

	.form-label {
		font-family: var(--font-mono);
		font-size: 11px;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		color: rgba(var(--color-text), 0.5);
	}

	.text-input {
		background-color: rgba(var(--color-bg), 0.5);
		border: 1px solid rgba(var(--color-accent), 0.15);
		color: rgb(var(--color-text));
		padding: 14px 20px;
		border-radius: 0px;
		font-family: var(--font-body);
		font-size: 14px;
		font-weight: 300;
		transition: border-color var(--transition-medium), background-color var(--transition-medium);
		outline: none;
		width: 100%;
	}

	.text-input:focus {
		border-color: rgba(var(--color-accent), 0.45);
		background-color: rgba(var(--color-bg), 0.85);
	}

	/* Options selector buttons grid */
	.options-grid {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 12px;
	}

	@media (max-width: 480px) {
		.options-grid {
			grid-template-columns: 1fr;
		}
	}

	.option-selector {
		background: rgba(var(--color-bg), 0.5);
		border: 1px solid rgba(var(--color-accent), 0.12);
		color: rgba(var(--color-text), 0.65);
		padding: 14px;
		cursor: pointer;
		text-align: left;
		transition: border-color var(--transition-medium), color var(--transition-medium), background-color var(--transition-medium);
		display: flex;
		flex-direction: column;
		gap: 4px;
	}

	.option-selector:hover {
		border-color: rgba(var(--color-accent), 0.3);
		color: rgb(var(--color-text));
	}

	.option-selector.selected {
		border-color: rgba(var(--color-text), 0.85);
		color: rgb(var(--color-text));
		background: rgba(255, 255, 255, 0.02);
	}

	.option-code {
		font-family: var(--font-mono);
		font-size: 9px;
		color: rgba(var(--color-accent), 0.45);
		letter-spacing: 0.1em;
	}

	.option-label {
		font-size: 13px;
		font-family: var(--font-body);
	}

	/* Range Slider styling */
	.slider-header {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
	}

	.slider-value {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgb(var(--color-pulse));
	}

	.range-slider {
		-webkit-appearance: none;
		appearance: none;
		width: 100%;
		height: 1px;
		background: rgba(var(--color-accent), 0.15);
		outline: none;
		margin: 12px 0;
	}

	.range-slider::-webkit-slider-thumb {
		-webkit-appearance: none;
		appearance: none;
		width: 12px;
		height: 12px;
		border-radius: 50%;
		background: rgb(var(--color-text));
		cursor: pointer;
		transition: transform var(--transition-fast), background-color var(--transition-fast);
	}

	.range-slider::-webkit-slider-thumb:hover {
		transform: scale(1.2);
		background: rgb(var(--color-pulse));
	}

	.slider-labels {
		display: flex;
		justify-content: space-between;
		font-family: var(--font-mono);
		font-size: 9px;
		color: rgba(var(--color-accent), 0.35);
		letter-spacing: 0.05em;
	}

	.btn-submit {
		width: 100%;
		justify-content: center;
		padding: 16px;
		cursor: pointer;
		border: none;
	}

	/* Dynamic Invoice Panel */
	:global(.receipt-card) {
		border: 1px solid rgba(var(--color-accent), 0.08);
		background-color: rgba(8, 8, 9, 0.95);
		position: sticky;
		top: 120px;
	}

	.receipt-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding-bottom: 8px;
	}

	.receipt-logo {
		font-family: var(--font-primary);
		font-size: 12px;
		letter-spacing: 0.15em;
		color: rgba(var(--color-text), 0.85);
	}

	.divider-dashed {
		border: none;
		border-top: 1px dashed rgba(var(--color-accent), 0.15);
		margin: 16px 0;
	}

	.receipt-specs {
		display: flex;
		flex-direction: column;
		gap: 16px;
	}

	.receipt-title {
		font-size: 1.4rem;
		text-transform: none;
		letter-spacing: normal;
		margin-bottom: 8px;
		color: rgb(var(--color-text));
	}

	.receipt-row {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		font-family: var(--font-mono);
		font-size: 11px;
		letter-spacing: 0.05em;
	}

	.r-key {
		color: rgba(var(--color-accent), 0.45);
	}

	.r-val {
		color: rgba(var(--color-text), 0.9);
		text-align: right;
		max-width: 60%;
		word-break: break-all;
	}

	.receipt-footer {
		border-top: 1px solid rgba(var(--color-accent), 0.08);
		padding-top: 20px;
		margin-top: 24px;
		text-align: center;
	}

	.technical-hash {
		font-family: var(--font-mono);
		font-size: 10px;
		color: rgba(var(--color-accent), 0.3);
		letter-spacing: 0.08em;
	}

	/* Success State Card */
	:global(.success-matrix-card) {
		max-width: 800px;
		margin: 0 auto;
		text-align: center;
		border: 1px solid rgba(var(--color-pulse), 0.15);
		background-color: rgba(6, 6, 7, 0.98);
		box-shadow: 0 30px 60px -25px rgba(0, 0, 0, 0.9);
	}

	.success-header {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 20px;
		margin-bottom: 30px;
	}

	.success-glowing-circle {
		width: 40px;
		height: 40px;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.success-badge {
		color: rgb(var(--color-pulse));
		border-color: rgba(var(--color-pulse), 0.2);
	}

	.success-body {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 24px;
	}

	.success-title {
		font-size: clamp(2rem, 4vw, 3rem);
		text-transform: none;
		letter-spacing: normal;
		color: rgb(var(--color-text));
	}

	.success-message {
		font-size: 1.05rem;
		line-height: 1.6;
		color: rgba(var(--color-text), 0.7);
		max-width: 600px;
		font-weight: 300;
	}

	.success-blueprint-receipt {
		width: 100%;
		max-width: 560px;
		background: rgba(var(--color-bg), 0.75);
		border: 1px solid rgba(var(--color-accent), 0.08);
		padding: 24px clamp(16px, 4vw, 32px);
		display: flex;
		flex-direction: column;
		gap: 16px;
		margin: 16px 0;
	}

	.s-row {
		display: flex;
		justify-content: space-between;
		align-items: center;
		font-family: var(--font-mono);
		font-size: 11px;
		letter-spacing: 0.05em;
	}

	.s-label {
		color: rgba(var(--color-accent), 0.45);
	}

	.s-info {
		color: rgba(var(--color-text), 0.9);
	}

	.font-mono-highlight {
		color: rgb(var(--color-pulse));
		font-weight: 500;
	}

	.btn-success-back {
		border: none;
		cursor: pointer;
	}
</style>
