<script>
	let { 
		title = '',
		description = '',
		children 
	} = $props();
</script>

<div class="about-card">
	{#if title}
		<h3 class="about-title">{title}</h3>
	{/if}
	{#if description}
		<p class="about-description">{description}</p>
	{/if}
	{#if children}
		<div class="about-extras">
			{@render children()}
		</div>
	{/if}
</div>

<style>
	.about-card {
		background: white;
		padding: 2rem;
		border-radius: 12px;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
	}

	.about-title {
		font-size: 1.5rem;
		font-weight: 600;
		color: #1f2937;
		margin-bottom: 1rem;
	}

	.about-description {
		color: #64748b;
		line-height: 1.8;
		font-size: 1.1rem;
	}

	.about-extras {
		margin-top: 1.5rem;
	}
</style>

