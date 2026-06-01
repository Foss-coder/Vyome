<script lang="ts">
	import type { Snippet } from 'svelte';

	let { 
		children, 
		class: className = '', 
		hoverEffect = true,
		padding = 'large',
		...restProps 
	} = $props<{
		children: Snippet;
		class?: string;
		hoverEffect?: boolean;
		padding?: 'none' | 'small' | 'large';
		[key: string]: any;
	}>();
</script>

<div 
	class="glass-panel interactive-card {className}"
	class:hover-trigger={hoverEffect}
	class:p-none={padding === 'none'}
	class:p-sm={padding === 'small'}
	class:p-lg={padding === 'large'}
	{...restProps}
>
	<!-- Decorative subtle corner bracket details to reinforce Master Architect blueprint feel -->
	<span class="corner-bracket top-left"></span>
	<span class="corner-bracket top-right"></span>
	<span class="corner-bracket bottom-left"></span>
	<span class="corner-bracket bottom-right"></span>

	{@render children()}
</div>

<style>
	.glass-panel {
		position: relative;
		border-radius: 0px; /* Monochromatic architectural sharp corners */
		overflow: hidden;
		transition: 
			border-color var(--transition-medium),
			background-color var(--transition-medium),
			transform var(--transition-slow),
			box-shadow var(--transition-slow);
	}

	/* Specific Padding Styles */
	.p-none {
		padding: 0;
	}
	
	.p-sm {
		padding: clamp(16px, 3vw, 24px);
	}

	.p-lg {
		padding: clamp(24px, 5vw, 48px);
	}

	/* Corner architectural brackets */
	.corner-bracket {
		position: absolute;
		width: 4px;
		height: 4px;
		border-color: rgba(var(--color-accent), 0.15);
		border-style: solid;
		pointer-events: none;
		transition: border-color var(--transition-medium);
	}

	.top-left {
		top: 8px;
		left: 8px;
		border-width: 1px 0 0 1px;
	}

	.top-right {
		top: 8px;
		right: 8px;
		border-width: 1px 1px 0 0;
	}

	.bottom-left {
		bottom: 8px;
		left: 8px;
		border-width: 0 0 1px 1px;
	}

	.bottom-right {
		bottom: 8px;
		right: 8px;
		border-width: 0 1px 1px 0;
	}

	/* Interactive card effects with heavy physical transition curves */
	.hover-trigger:hover {
		transform: translateY(-2px);
		border-color: rgba(var(--color-accent), 0.18);
		background-color: rgba(10, 10, 11, 0.85);
		box-shadow: 
			0 20px 40px -15px rgba(0, 0, 0, 0.7),
			inset 0 0 12px rgba(255, 255, 255, 0.01);
	}

	.hover-trigger:hover .corner-bracket {
		border-color: rgba(var(--color-accent), 0.4);
	}
</style>
