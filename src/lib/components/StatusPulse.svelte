<script lang="ts">
	let { 
		statusText = 'SYSTEM ACTIVE', 
		showText = true, 
		size = 'md' 
	} = $props();
</script>

<div class="pulse-container" class:size-sm={size === 'sm'} class:size-md={size === 'md'}>
	<div class="indicator">
		<div class="dot pulse-animation"></div>
		<div class="ring"></div>
	</div>
	{#if showText}
		<span class="label">{statusText}</span>
	{/if}
</div>

<style>
	.pulse-container {
		display: inline-flex;
		align-items: center;
		gap: 12px;
		user-select: none;
	}

	.indicator {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.size-md .indicator {
		width: 12px;
		height: 12px;
	}

	.size-sm .indicator {
		width: 8px;
		height: 8px;
	}

	.dot {
		background-color: rgb(var(--color-pulse));
		border-radius: 50%;
		z-index: 2;
	}

	.size-md .dot {
		width: 10px;
		height: 10px;
	}

	.size-sm .dot {
		width: 6px;
		height: 6px;
	}

	.ring {
		position: absolute;
		border: 1px solid rgba(var(--color-pulse), 0.6);
		border-radius: 50%;
		z-index: 1;
		opacity: 0;
		animation: ringExpand 2.4s infinite cubic-bezier(0.16, 1, 0.3, 1);
	}

	.size-md .ring {
		width: 10px;
		height: 10px;
	}

	.size-sm .ring {
		width: 6px;
		height: 6px;
	}

	.label {
		font-family: var(--font-mono);
		font-size: 11px;
		letter-spacing: 0.15em;
		color: rgba(var(--color-text), 0.65);
		text-transform: uppercase;
		font-weight: 400;
	}

	.size-sm .label {
		font-size: 10px;
	}

	@keyframes ringExpand {
		0% {
			transform: scale(1);
			opacity: 0.8;
		}
		100% {
			transform: scale(3.5);
			opacity: 0;
		}
	}
</style>
