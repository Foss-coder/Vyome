<script lang="ts">
import { onMount } from 'svelte';
import '../app.css';

let cursorEl: HTMLDivElement | null = null;
let mouseX = -100;
let mouseY = -100;
let cursorX = -100;
let cursorY = -100;
let isHovering = false;

onMount(() => {
	const handleMouseMove = (event: MouseEvent) => {
		mouseX = event.clientX;
		mouseY = event.clientY;
	};

	const handlePointer = (event: MouseEvent) => {
		const target = event.target as HTMLElement;
		isHovering = Boolean(target.closest('a') || target.closest('button'));
	};

	window.addEventListener('mousemove', handleMouseMove);
	window.addEventListener('mouseover', handlePointer);

	let frameId: number;
	const follow = () => {
		const dx = mouseX - cursorX;
		const dy = mouseY - cursorY;
		cursorX += dx * 0.12;
		cursorY += dy * 0.12;

		if (cursorEl) {
			cursorEl.style.transform = `translate3d(${cursorX - 8}px, ${cursorY - 8}px, 0)`;
			cursorEl.style.opacity = mouseX < 0 ? '0' : '1';
		}

		frameId = requestAnimationFrame(follow);
	};

	follow();

	return () => {
		window.removeEventListener('mousemove', handleMouseMove);
		window.removeEventListener('mouseover', handlePointer);
		cancelAnimationFrame(frameId);
	};
});
</script>

<svelte:head>
	<title>VYOME | Architectural Digital Ecosystems</title>
	<meta name="description" content="We architect premium digital ecosystems and luxury digital real estate for resorts, fashion, real estate, and architecture." />
	<link rel="icon" type="image/svg+xml" href="/favicon.svg" />
</svelte:head>

<div class="page-shell">
	<div class="site-shell">
		<header class="site-nav">
			<a class="nav-brand" href="/">VYOME</a>
			<nav class="nav-links">
				<a href="/work">Work</a>
				<a href="/services">Services</a>
				<a href="/contact">Contact</a>
			</nav>
		</header>

		<main>
			<slot />
		</main>

		<footer class="page-footer">
			<p class="footer-copy">VYOME · We architect high-end digital ecosystems</p>
			<p class="footer-copy">2026 | Exclusive digital atelier for luxury experiences</p>
		</footer>
	</div>
</div>

<div bind:this={cursorEl} class:hovering={isHovering} class="custom-cursor"></div>
