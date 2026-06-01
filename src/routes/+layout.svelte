<script lang="ts">
	import '../app.css';
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import favicon from '$lib/assets/favicon.svg';
	import { onMount } from 'svelte';

	let { children } = $props();

	// Custom physical cursor tracking for elite interactive finish
	let cursorEl: HTMLDivElement | null = $state(null);
	let mouseX = $state(-100);
	let mouseY = $state(-100);
	let cursorX = $state(-100);
	let cursorY = $state(-100);
	let isHoveringInteractable = $state(false);

	onMount(() => {
		const handleMouseMove = (e: MouseEvent) => {
			mouseX = e.clientX;
			mouseY = e.clientY;
		};

		const handleMouseOver = (e: MouseEvent) => {
			const target = e.target as HTMLElement;
			if (
				target.closest('a') || 
				target.closest('button') || 
				target.closest('.interactive-card') ||
				target.closest('[role="button"]')
			) {
				isHoveringInteractable = true;
			} else {
				isHoveringInteractable = false;
			}
		};

		window.addEventListener('mousemove', handleMouseMove);
		window.addEventListener('mouseover', handleMouseOver);

		// Physics-based custom animation frame loop to follow mouse heavily (luxury damping)
		let frameId: number;
		const tick = () => {
			const dx = mouseX - cursorX;
			const dy = mouseY - cursorY;
			cursorX += dx * 0.08; // Small factor = heavy damping
			cursorY += dy * 0.08;

			if (cursorEl) {
				cursorEl.style.transform = `translate3d(${cursorX}px, ${cursorY}px, 0) scale(${isHoveringInteractable ? 1.6 : 1})`;
				cursorEl.style.opacity = mouseX < 0 ? '0' : '1';
			}
			frameId = requestAnimationFrame(tick);
		};

		tick();

		return () => {
			window.removeEventListener('mousemove', handleMouseMove);
			window.removeEventListener('mouseover', handleMouseOver);
			cancelAnimationFrame(frameId);
		};
	});
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>VYOME | Architectural Digital Ecosystems</title>
	<meta name="description" content="We architect premium, high-end digital transformation platforms and ecosystems for luxury hotels, fashion brands, real estate, and architectural practices." />
	<!-- Preload Clash Display and Satoshi -->
	<link rel="preconnect" href="https://api.fontshare.com" />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
</svelte:head>

<!-- Premium Physical Cursor Overlay (Invisible on touch devices via CSS hover queries) -->
<div 
	bind:this={cursorEl} 
	class="custom-cursor"
	class:hovering={isHoveringInteractable}
></div>

<div class="app-viewport">
	<Header />
	
	<main class="main-content">
		{@render children()}
	</main>

	<Footer />
</div>

<style>
	.app-viewport {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		background-color: rgb(var(--color-bg));
		position: relative;
	}

	.main-content {
		flex: 1 0 auto;
		z-index: 10;
	}

	/* Custom cursor styling */
	.custom-cursor {
		position: fixed;
		top: -10px;
		left: -10px;
		width: 20px;
		height: 20px;
		border: 1px solid rgba(var(--color-accent), 0.4);
		border-radius: 50%;
		pointer-events: none;
		z-index: 9999;
		mix-blend-mode: difference;
		transition: width 0.3s var(--ease-luxury), 
					height 0.3s var(--ease-luxury), 
					border-color 0.3s var(--ease-luxury), 
					background-color 0.3s var(--ease-luxury);
		opacity: 0;
	}

	.custom-cursor.hovering {
		background-color: rgba(var(--color-accent), 0.1);
		border-color: rgba(var(--color-accent), 0.8);
	}

	@media (pointer: coarse) {
		.custom-cursor {
			display: none;
		}
	}
</style>
