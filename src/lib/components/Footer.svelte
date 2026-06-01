<script lang="ts">
	import { onMount } from 'svelte';

	let localTime = $state('');

	onMount(() => {
		const updateTime = () => {
			const date = new Date();
			const options: Intl.DateTimeFormatOptions = {
				timeZone: 'Asia/Kolkata', // Set to Indian Standard Time (matching GMT+5:30 in user context)
				hour: '2-digit',
				minute: '2-digit',
				second: '2-digit',
				hour12: false
			};
			const timeString = date.toLocaleTimeString('en-US', options);
			localTime = `IST ${timeString}`;
		};

		updateTime();
		const interval = setInterval(updateTime, 1000);

		return () => clearInterval(interval);
	});
</script>

<footer class="studio-footer">
	<hr class="divider-platinum" />

	<div class="footer-container section-spacer">
		<div class="footer-grid">
			<!-- Column 1: Editorial Positioning -->
			<div class="footer-col col-brand">
				<a href="/" class="brand-logo-small">
					<span class="logo-text">VYOME</span>
					<span class="logo-dot"></span>
				</a>
				<p class="brand-bio">
					Architecting premium, high-end digital transformation platforms and digital ecosystems for luxury markets.
				</p>
				<div class="tech-badge">
					<span class="status-dot"></span>
					<span>ATELIER OPEN</span>
				</div>
			</div>

			<!-- Column 2: Ecosystems -->
			<div class="footer-col">
				<h4 class="col-title">Ecosystems</h4>
				<ul class="col-links">
					<li><a href="/ecosystems">Luxury Hospitality</a></li>
					<li><a href="/ecosystems">High Fashion</a></li>
					<li><a href="/ecosystems">Architectural Portals</a></li>
					<li><a href="/ecosystems">Elite Real Estate</a></li>
				</ul>
			</div>

			<!-- Column 3: Architecture -->
			<div class="footer-col">
				<h4 class="col-title">Atelier</h4>
				<ul class="col-links">
					<li><a href="/architects">The Blueprint</a></li>
					<li><a href="/architects">AI Orchestration</a></li>
					<li><a href="/architects">Technical Core</a></li>
					<li><a href="/studio">The Workspace</a></li>
				</ul>
			</div>

			<!-- Column 4: Studio Metadata -->
			<div class="footer-col col-meta">
				<h4 class="col-title">Studio Core</h4>
				<div class="meta-block">
					<p class="mono-meta">[ REGION: GLOBAL ]</p>
					<p class="mono-meta">[ LOC: GMT+5:30 ]</p>
					<p class="mono-meta">[ CLOCK: {localTime || 'LOADING...'} ]</p>
					<p class="mono-meta">[ PORT: SECURE_HTTPS ]</p>
				</div>
			</div>
		</div>

		<!-- Legal Details & System Status -->
		<div class="footer-bottom">
			<p class="copyright">
				&copy; {new Date().getFullYear()} VYOME STUDIO. ALL RIGHTS RESERVED.
			</p>
			
			<div class="status-indicator-footer">
				<span class="mono-version">[ SYSTEM VERSION: V2.6.1_PROD ]</span>
			</div>
		</div>
	</div>
</footer>

<style>
	.studio-footer {
		background-color: rgb(var(--color-bg));
		width: 100%;
		flex-shrink: 0;
	}

	.footer-container {
		padding-top: clamp(60px, 8vw, 100px);
		padding-bottom: 60px;
		max-width: 1440px;
		margin: 0 auto;
		padding-left: clamp(24px, 6vw, 120px);
		padding-right: clamp(24px, 6vw, 120px);
	}

	.footer-grid {
		display: grid;
		grid-template-columns: 2fr 1fr 1fr 1.5fr;
		gap: 60px;
		margin-bottom: 80px;
	}

	@media (max-width: 1024px) {
		.footer-grid {
			grid-template-columns: 1.5fr 1fr 1fr;
			gap: 40px;
		}
		
		.col-meta {
			grid-column: span 3;
			border-top: 1px solid rgba(var(--color-accent), 0.08);
			padding-top: 30px;
		}
	}

	@media (max-width: 768px) {
		.footer-grid {
			grid-template-columns: 1fr;
			gap: 40px;
		}
		
		.col-meta {
			grid-column: span 1;
		}
	}

	.footer-col {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		gap: 20px;
	}

	/* Brand Column styling */
	.brand-logo-small {
		display: flex;
		align-items: center;
		gap: 5px;
		text-decoration: none;
		color: rgb(var(--color-text));
	}

	.brand-logo-small .logo-text {
		font-family: var(--font-primary);
		font-size: 1.1rem;
		font-weight: 500;
		letter-spacing: 0.2em;
	}

	.brand-logo-small .logo-dot {
		width: 3px;
		height: 3px;
		border-radius: 50%;
		background-color: rgb(var(--color-pulse));
		box-shadow: 0 0 6px rgb(var(--color-pulse));
	}

	.brand-bio {
		font-size: 0.95rem;
		line-height: 1.6;
		color: rgba(var(--color-text), 0.55);
		max-width: 280px;
	}

	/* Link columns */
	.col-title {
		font-family: var(--font-primary);
		font-size: 0.75rem;
		letter-spacing: 0.2em;
		color: rgba(var(--color-text), 0.4);
		text-transform: uppercase;
		margin-bottom: 4px;
	}

	.col-links {
		list-style: none;
		display: flex;
		flex-direction: column;
		gap: 12px;
	}

	.col-links a {
		font-family: var(--font-body);
		font-size: 0.95rem;
		color: rgba(var(--color-text), 0.6);
		text-decoration: none;
		transition: color var(--transition-fast), transform var(--transition-fast);
		display: inline-block;
	}

	.col-links a:hover {
		color: rgb(var(--color-text));
		transform: translateX(2px);
	}

	/* Meta block styling */
	.meta-block {
		display: flex;
		flex-direction: column;
		gap: 8px;
	}

	.mono-meta {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.5);
		letter-spacing: 0.12em;
		text-transform: uppercase;
	}

	/* Footer bottom */
	.footer-bottom {
		border-top: 1px solid rgba(var(--color-accent), 0.08);
		padding-top: 40px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		gap: 20px;
		flex-wrap: wrap;
	}

	.copyright {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.08em;
	}

	.mono-version {
		font-family: var(--font-mono);
		font-size: 10px;
		color: rgba(var(--color-accent), 0.3);
		letter-spacing: 0.1em;
	}
</style>
