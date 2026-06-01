<script lang="ts">
	export let statusText = 'SYSTEM ACTIVE';
</script>

<div class="status-pulse"><span class="status-dot"></span><span>{statusText}</span></div>

<style>
	.status-pulse {
		display: inline-flex;
		align-items: center;
		gap: 0.75rem;
		font-family: var(--font-mono);
		font-size: 0.75rem;
		letter-spacing: 0.16em;
		text-transform: uppercase;
		color: rgba(var(--color-accent), 0.95);
	}

	.status-pulse .status-dot {
		width: 10px;
		height: 10px;
		border-radius: 50%;
		background: rgb(var(--color-pulse));
		box-shadow: 0 0 12px rgba(var(--color-pulse), 0.4);
	}
</style>
