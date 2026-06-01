<script lang="ts">
	import StatusPulse from './StatusPulse.svelte';
	import { page } from '$app/state';

	let isMobileMenuOpen = $state(false);

	const navLinks = [
		{ href: '/ecosystems', label: 'Ecosystems' },
		{ href: '/architects', label: 'Architects' },
		{ href: '/studio', label: 'Atelier Studio' }
	];

	function toggleMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}

	function closeMenu() {
		isMobileMenuOpen = false;
	}
</script>

<header class="studio-header">
	<div class="header-container">
		<!-- Brand Logo -->
		<a href="/" class="brand-logo" onclick={closeMenu}>
			<span class="logo-text">VYOME</span>
			<span class="logo-dot"></span>
		</a>

		<!-- System Status (Desktop) -->
		<div class="system-status-desktop">
			<StatusPulse statusText="SYSTEM: OPERATIONAL" size="sm" />
		</div>

		<!-- Main Navigation (Desktop) -->
		<nav class="nav-desktop">
			{#each navLinks as link}
				{@const isActive = page.url.pathname === link.href}
				<a 
					href={link.href} 
					class="nav-link" 
					class:active={isActive}
				>
					<span class="nav-char">[</span>
					<span class="nav-label">{link.label}</span>
					<span class="nav-char">]</span>
					<span class="nav-line"></span>
				</a>
			{/each}
		</nav>

		<!-- Mobile Menu Trigger -->
		<button 
			class="mobile-trigger" 
			class:open={isMobileMenuOpen} 
			onclick={toggleMenu} 
			aria-label="Toggle menu"
		>
			<span class="bar bar-top"></span>
			<span class="bar bar-bottom"></span>
		</button>
	</div>

	<!-- System Divider -->
	<hr class="divider-platinum" />

	<!-- Mobile Menu Drawer (Overlay) -->
	{#if isMobileMenuOpen}
		<div class="mobile-drawer">
			<div class="drawer-header">
				<StatusPulse statusText="SECURE LINK: ACTIVE" size="sm" />
			</div>
			
			<nav class="nav-mobile">
				{#each navLinks as link}
					{@const isActive = page.url.pathname === link.href}
					<a 
						href={link.href} 
						class="mobile-nav-link" 
						class:active={isActive}
						onclick={closeMenu}
					>
						<span class="mobile-num">0{navLinks.indexOf(link) + 1}</span>
						<span class="mobile-label">{link.label}</span>
					</a>
				{/each}
			</nav>

			<div class="drawer-footer">
				<p class="mono-meta">[ LATITUDE: 28.6139° N ]</p>
				<p class="mono-meta">[ LONGITUDE: 77.2090° E ]</p>
			</div>
		</div>
	{/if}
</header>

<style>
	.studio-header {
		position: sticky;
		top: 0;
		left: 0;
		width: 100%;
		z-index: 100;
		background: rgba(10, 10, 11, 0.85);
		backdrop-filter: blur(16px);
		-webkit-backdrop-filter: blur(16px);
	}

	.header-container {
		max-width: 1440px;
		margin: 0 auto;
		height: 80px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 0 clamp(24px, 6vw, 120px);
	}

	/* Logo Styling */
	.brand-logo {
		display: flex;
		align-items: center;
		gap: 6px;
		text-decoration: none;
		color: rgb(var(--color-text));
		transition: transform var(--transition-fast);
	}

	.brand-logo:hover {
		transform: scale(1.02);
	}

	.logo-text {
		font-family: var(--font-primary);
		font-size: 1.35rem;
		font-weight: 600;
		letter-spacing: 0.25em;
	}

	.logo-dot {
		width: 4px;
		height: 4px;
		border-radius: 50%;
		background-color: rgb(var(--color-pulse));
		box-shadow: 0 0 8px rgb(var(--color-pulse));
	}

	/* System Status (Desktop) */
	.system-status-desktop {
		display: block;
	}

	@media (max-width: 768px) {
		.system-status-desktop {
			display: none;
		}
	}

	/* Nav Desktop */
	.nav-desktop {
		display: flex;
		align-items: center;
		gap: clamp(16px, 3vw, 40px);
	}

	@media (max-width: 768px) {
		.nav-desktop {
			display: none;
		}
	}

	.nav-link {
		position: relative;
		font-family: var(--font-mono);
		font-size: 12px;
		letter-spacing: 0.12em;
		text-transform: uppercase;
		color: rgba(var(--color-text), 0.6);
		text-decoration: none;
		padding: 8px 0;
		display: flex;
		align-items: center;
		transition: color var(--transition-medium);
	}

	.nav-char {
		opacity: 0;
		transition: opacity var(--transition-medium), transform var(--transition-medium);
		color: rgba(var(--color-accent), 0.4);
	}
	
	.nav-char:first-child {
		transform: translateX(4px);
	}

	.nav-char:last-child {
		transform: translateX(-4px);
	}

	.nav-link:hover,
	.nav-link.active {
		color: rgb(var(--color-text));
	}

	.nav-link:hover .nav-char,
	.nav-link.active .nav-char {
		opacity: 1;
		transform: translateX(0);
	}

	.nav-label {
		padding: 0 4px;
	}

	.nav-line {
		position: absolute;
		bottom: 0;
		left: 50%;
		width: 0;
		height: 1px;
		background-color: rgb(var(--color-accent));
		transition: width var(--transition-medium), left var(--transition-medium);
	}

	.nav-link:hover .nav-line,
	.nav-link.active .nav-line {
		width: 100%;
		left: 0;
	}

	/* Mobile Burger Trigger */
	.mobile-trigger {
		display: none;
		flex-direction: column;
		justify-content: center;
		gap: 6px;
		width: 32px;
		height: 32px;
		background: none;
		border: none;
		cursor: pointer;
		z-index: 110;
	}

	@media (max-width: 768px) {
		.mobile-trigger {
			display: flex;
		}
	}

	.bar {
		width: 24px;
		height: 1px;
		background-color: rgb(var(--color-text));
		transition: transform var(--transition-medium), background-color var(--transition-medium);
	}

	.mobile-trigger.open .bar-top {
		transform: translateY(3.5px) rotate(45deg);
	}

	.mobile-trigger.open .bar-bottom {
		transform: translateY(-3.5px) rotate(-45deg);
	}

	/* Mobile Menu Drawer Overlay */
	.mobile-drawer {
		position: fixed;
		top: 80px;
		left: 0;
		width: 100%;
		height: calc(100vh - 80px);
		background-color: rgb(var(--color-bg));
		z-index: 95;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		padding: 40px clamp(24px, 6vw, 120px) 80px clamp(24px, 6vw, 120px);
		animation: drawerSlide 0.6s var(--ease-luxury) forwards;
	}

	@keyframes drawerSlide {
		from {
			opacity: 0;
			transform: translateY(-10px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.drawer-header {
		border-bottom: 1px solid rgba(var(--color-accent), 0.1);
		padding-bottom: 20px;
	}

	.nav-mobile {
		display: flex;
		flex-direction: column;
		gap: 32px;
		margin: 40px 0;
	}

	.mobile-nav-link {
		display: flex;
		align-items: baseline;
		gap: 16px;
		text-decoration: none;
		color: rgba(var(--color-text), 0.55);
		transition: color var(--transition-medium), transform var(--transition-medium);
	}

	.mobile-nav-link:hover,
	.mobile-nav-link.active {
		color: rgb(var(--color-text));
		transform: translateX(8px);
	}

	.mobile-num {
		font-family: var(--font-mono);
		font-size: 12px;
		color: rgba(var(--color-accent), 0.4);
	}

	.mobile-label {
		font-family: var(--font-primary);
		font-size: 2.2rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
	}

	.drawer-footer {
		border-top: 1px solid rgba(var(--color-accent), 0.1);
		padding-top: 20px;
		display: flex;
		flex-direction: column;
		gap: 8px;
	}

	.mono-meta {
		font-family: var(--font-mono);
		font-size: 11px;
		color: rgba(var(--color-accent), 0.4);
		letter-spacing: 0.1em;
	}
</style>
