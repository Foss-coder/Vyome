<script lang="ts">
	let { 
		type = 'cube', 
		size = 64, 
		color = 'rgba(var(--color-accent), 0.8)' 
	} = $props();
</script>

<div 
	class="blueprint-wrapper" 
	style="--size: {size}px; --stroke-color: {color};"
>
	{#if type === 'cube'}
		<!-- Web Architect: Isometric 3D Wireframe Cube with Construction Lines -->
		<svg 
			class="traceable-svg" 
			viewBox="0 0 100 100" 
			fill="none" 
			stroke="currentColor" 
			stroke-width="1" 
			stroke-linecap="round" 
			stroke-linejoin="round"
		>
			<!-- Outer boundary / construction box -->
			<rect x="5" y="5" width="90" height="90" stroke="currentColor" stroke-dasharray="2 4" stroke-opacity="0.25" />
			
			<!-- Blueprint corner markers -->
			<line x1="5" y1="15" x2="5" y2="5" />
			<line x1="5" y1="5" x2="15" y2="5" />
			
			<line x1="95" y1="15" x2="95" y2="5" />
			<line x1="95" y1="5" x2="85" y2="5" />
			
			<line x1="5" y1="85" x2="5" y2="95" />
			<line x1="5" y1="95" x2="15" y2="95" />
			
			<line x1="95" y1="85" x2="95" y2="95" />
			<line x1="95" y1="95" x2="85" y2="95" />

			<!-- Central Isometric Cube Wireframe Paths -->
			<!-- Vertical lines -->
			<line x1="50" y1="15" x2="50" y2="50" class="path-main" />
			<line x1="50" y1="50" x2="50" y2="85" class="path-main" />
			<line x1="20" y1="32" x2="20" y2="68" class="path-secondary" />
			<line x1="80" y1="32" x2="80" y2="68" class="path-secondary" />
			
			<!-- Slanted top faces -->
			<line x1="50" y1="15" x2="20" y2="32" class="path-main" />
			<line x1="50" y1="15" x2="80" y2="32" class="path-main" />
			<line x1="20" y1="32" x2="50" y2="50" class="path-main" />
			<line x1="80" y1="32" x2="50" y2="50" class="path-main" />
			
			<!-- Slanted bottom faces -->
			<line x1="20" y1="68" x2="50" y2="85" class="path-main" />
			<line x1="80" y1="68" x2="50" y2="85" class="path-main" />
			
			<!-- Inner wireframe projection (back edges) -->
			<line x1="20" y1="32" x2="50" y2="50" class="path-back" stroke-dasharray="2 2" stroke-opacity="0.4" />
			<line x1="80" y1="32" x2="50" y2="50" class="path-back" stroke-dasharray="2 2" stroke-opacity="0.4" />
			<line x1="50" y1="85" x2="50" y2="50" class="path-back" stroke-dasharray="2 2" stroke-opacity="0.4" />
			
			<!-- Architectural projection lines extending outward -->
			<line x1="50" y1="15" x2="50" y2="5" stroke-dasharray="1 3" stroke-opacity="0.5" />
			<line x1="50" y1="85" x2="50" y2="95" stroke-dasharray="1 3" stroke-opacity="0.5" />
			<line x1="20" y1="32" x2="10" y2="26" stroke-dasharray="1 3" stroke-opacity="0.5" />
			<line x1="80" y1="32" x2="90" y2="26" stroke-dasharray="1 3" stroke-opacity="0.5" />
			
			<!-- Node markers -->
			<circle cx="50" cy="15" r="1.5" fill="currentColor" />
			<circle cx="50" cy="50" r="2" fill="currentColor" />
			<circle cx="50" cy="85" r="1.5" fill="currentColor" />
			<circle cx="20" cy="32" r="1.5" fill="currentColor" />
			<circle cx="80" cy="32" r="1.5" fill="currentColor" />
			<circle cx="20" cy="68" r="1.5" fill="currentColor" />
			<circle cx="80" cy="68" r="1.5" fill="currentColor" />
		</svg>

	{:else if type === 'waveform'}
		<!-- AI Engine: Interlocking orbital spheres and geometric waveforms -->
		<svg 
			class="traceable-svg" 
			viewBox="0 0 100 100" 
			fill="none" 
			stroke="currentColor" 
			stroke-width="1" 
			stroke-linecap="round" 
			stroke-linejoin="round"
		>
			<!-- Circular compass boundary -->
			<circle cx="50" cy="50" r="45" stroke="currentColor" stroke-dasharray="2 4" stroke-opacity="0.25" />
			
			<!-- Outer axis indicators -->
			<line x1="50" y1="2" x2="50" y2="8" />
			<line x1="50" y1="92" x2="50" y2="98" />
			<line x1="2" y1="50" x2="8" y2="50" />
			<line x1="92" y1="50" x2="98" y2="50" />
			
			<!-- Horizontal technical waveform line -->
			<line x1="10" y1="50" x2="90" y2="50" stroke-opacity="0.15" />

			<!-- Interactive geometric waveforms (overlapping sine-like curves) -->
			<!-- Wave 1 (Upper primary) -->
			<path d="M 15 50 C 25 30, 35 30, 50 50 C 65 70, 75 70, 85 50" class="path-main" />
			<!-- Wave 2 (Lower phase-shifted) -->
			<path d="M 15 50 C 25 70, 35 70, 50 50 C 65 30, 75 30, 85 50" class="path-secondary" stroke-opacity="0.7" />
			<!-- Wave 3 (High-frequency technical weave) -->
			<path d="M 20 50 C 30 60, 40 40, 50 50 C 60 60, 70 40, 80 50" class="path-back" stroke-dasharray="3 3" stroke-opacity="0.5" />

			<!-- Central Orbital Ring (AI Core) -->
			<circle cx="50" cy="50" r="14" class="path-main" />
			<!-- Tilted orbital orbit -->
			<ellipse cx="50" cy="50" rx="22" ry="6" transform="rotate(-30 50 50)" class="path-secondary" stroke-opacity="0.6" />
			<ellipse cx="50" cy="50" rx="22" ry="6" transform="rotate(30 50 50)" class="path-secondary" stroke-opacity="0.6" />

			<!-- Nodes and markers -->
			<circle cx="50" cy="50" r="2.5" fill="currentColor" />
			<circle cx="32" cy="59" r="1.5" fill="currentColor" />
			<circle cx="68" cy="41" r="1.5" fill="currentColor" />
			<circle cx="50" cy="22" r="1.5" fill="currentColor" />
			<circle cx="50" cy="78" r="1.5" fill="currentColor" />
		</svg>

	{:else if type === 'matrix'}
		<!-- Automation Matrix: Sharp, single-stroke conveyor networks and nodes -->
		<svg 
			class="traceable-svg" 
			viewBox="0 0 100 100" 
			fill="none" 
			stroke="currentColor" 
			stroke-width="1" 
			stroke-linecap="round" 
			stroke-linejoin="round"
		>
			<!-- 90-degree blueprint grid system -->
			<line x1="20" y1="10" x2="20" y2="90" stroke-dasharray="1 5" stroke-opacity="0.15" />
			<line x1="50" y1="10" x2="50" y2="90" stroke-dasharray="1 5" stroke-opacity="0.15" />
			<line x1="80" y1="10" x2="80" y2="90" stroke-dasharray="1 5" stroke-opacity="0.15" />
			<line x1="10" y1="20" x2="90" y2="20" stroke-dasharray="1 5" stroke-opacity="0.15" />
			<line x1="10" y1="50" x2="90" y2="50" stroke-dasharray="1 5" stroke-opacity="0.15" />
			<line x1="10" y1="80" x2="90" y2="80" stroke-dasharray="1 5" stroke-opacity="0.15" />

			<!-- Main automation bus (90-degree conveyor lines) -->
			<!-- Path 1 (Horizontal routing) -->
			<path d="M 15 20 H 50 V 50 H 85" class="path-main" />
			<!-- Path 2 (Z-shape flow) -->
			<path d="M 15 80 H 50 V 50" class="path-secondary" />
			<!-- Path 3 (Vertical bypass) -->
			<path d="M 80 20 V 80 H 65" class="path-back" stroke-dasharray="2 2" stroke-opacity="0.5" />

			<!-- Linear transmission nodes -->
			<circle cx="15" cy="20" r="2.5" fill="currentColor" />
			<circle cx="50" cy="20" r="1.5" fill="currentColor" />
			<circle cx="50" cy="50" r="3" fill="currentColor" />
			<circle cx="85" cy="50" r="2" fill="currentColor" />
			<circle cx="15" cy="80" r="2.5" fill="currentColor" />
			<circle cx="80" cy="20" r="1.5" fill="currentColor" />
			<circle cx="80" cy="80" r="2" fill="currentColor" />
			<circle cx="65" cy="80" r="1.5" fill="currentColor" />

			<!-- Custom data boxes indicating active flow -->
			<rect x="25" y="15" width="10" height="10" class="path-secondary" stroke-width="0.75" />
			<line x1="27" y1="20" x2="33" y2="20" stroke-width="0.75" />

			<rect x="65" y="45" width="10" height="10" class="path-secondary" stroke-width="0.75" />
			<line x1="67" y1="50" x2="73" y2="50" stroke-width="0.75" />
		</svg>
	{/if}
</div>

<style>
	.blueprint-wrapper {
		width: var(--size);
		height: var(--size);
		color: var(--stroke-color);
		display: flex;
		align-items: center;
		justify-content: center;
		transition: transform var(--transition-slow);
	}

	.traceable-svg {
		width: 100%;
		height: 100%;
		overflow: visible;
	}

	/* Path Tracing setup: Initialize offsets high to draw them in */
	.path-main,
	.path-secondary,
	.path-back {
		stroke-dasharray: 350;
		stroke-dashoffset: 350;
		animation: drawIn 2.5s var(--ease-luxury) forwards;
	}

	.path-main {
		animation-delay: 0.1s;
	}

	.path-secondary {
		animation-delay: 0.3s;
	}

	.path-back {
		animation-delay: 0.5s;
		stroke-dasharray: 200;
		stroke-dashoffset: 200;
	}

	/* On Hover: Trigger Redrawing/Tracing of paths */
	/* We check for hovering of parent wrappers via global selectors or local hover */
	.blueprint-wrapper:hover {
		transform: scale(1.05) rotate(1deg);
	}

	.blueprint-wrapper:hover .path-main,
	:global(.interactive-card:hover) .path-main {
		animation: tracePath 1.6s var(--ease-luxury) forwards;
	}

	.blueprint-wrapper:hover .path-secondary,
	:global(.interactive-card:hover) .path-secondary {
		animation: tracePath 1.8s var(--ease-luxury) forwards;
	}

	.blueprint-wrapper:hover .path-back,
	:global(.interactive-card:hover) .path-back {
		animation: tracePath 2s var(--ease-luxury) forwards;
	}

	/* CSS Animations */
	@keyframes drawIn {
		0% {
			stroke-dashoffset: 350;
		}
		100% {
			stroke-dashoffset: 0;
		}
	}

	@keyframes tracePath {
		0% {
			stroke-dashoffset: 0;
		}
		50% {
			stroke-dashoffset: 350;
		}
		100% {
			stroke-dashoffset: 0;
		}
	}
</style>
