<script lang="ts">
	export let padding: 'compact' | 'default' = 'default';
	export let className = '';
</script>

<div class={`glass-panel ${padding === 'compact' ? 'glass-compact' : ''} ${className}`}>
	<slot />
</div>
