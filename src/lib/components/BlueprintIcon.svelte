<script lang="ts">
	export let type: 'cube' | 'waveform' | 'matrix' = 'cube';
	export let size = 72;
</script>

<svg
	width={size}
	height={size}
	viewBox="0 0 120 120"
	fill="none"
	xmlns="http://www.w3.org/2000/svg"
	class="traceable-svg"
>
	{#if type === 'cube'}
		<path d="M24 36L60 16L96 36V80L60 100L24 80V36Z" stroke="currentColor" stroke-width="2" stroke-linejoin="round" />
		<path d="M24 36L60 56L96 36" stroke="currentColor" stroke-width="2" />
		<path d="M60 56V100" stroke="currentColor" stroke-width="2" />
	{/if}
	{#if type === 'waveform'}
		<path d="M16 64C30 44 38 30 52 30C66 30 74 46 88 46C102 46 110 34 110 34" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
		<path d="M16 78C30 98 42 110 56 110C72 110 80 92 94 92C108 92 110 88 110 88" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
	{/if}
	{#if type === 'matrix'}
		<path d="M22 32H98" stroke="currentColor" stroke-width="2" />
		<path d="M22 60H98" stroke="currentColor" stroke-width="2" />
		<path d="M22 88H98" stroke="currentColor" stroke-width="2" />
		<path d="M22 32V88" stroke="currentColor" stroke-width="2" />
		<path d="M60 32V88" stroke="currentColor" stroke-width="2" />
		<path d="M98 32V88" stroke="currentColor" stroke-width="2" />
	{/if}
</svg>

<style>
	.traceable-svg {
		stroke: rgb(var(--color-accent));
		opacity: 0.95;
		stroke-dasharray: 240;
		stroke-dashoffset: 240;
		transition: stroke-dashoffset 0.92s var(--ease-luxury), opacity 0.4s ease;
	}

	.traceable-svg:hover {
		stroke-dashoffset: 0;
	}
</style>
