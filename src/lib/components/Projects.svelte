<script>
	let { 
		title = '',
		description = '',
		imageUrl = '',
		children 
	} = $props();
</script>

<article class="project-card">
	{#if imageUrl}
		<div class="project-image">
			<img src={imageUrl} alt={title} />
		</div>
	{/if}
	<div class="project-content">
		<h3 class="project-title">{title}</h3>
		{#if description}
			<p class="project-description">{description}</p>
		{/if}
		{#if children}
			<div class="project-links">
				{@render children()}
			</div>
		{/if}
	</div>
</article>

<style>
	.project-card {
		background: white;
		border-radius: 12px;
		overflow: hidden;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
		transition: transform 0.3s ease, box-shadow 0.3s ease;
	}

	.project-card:hover {
		transform: translateY(-4px);
		box-shadow: 0 12px 24px rgba(0, 0, 0, 0.1);
	}

	.project-image {
		width: 100%;
		height: 200px;
		overflow: hidden;
	}

	.project-image img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: transform 0.3s ease;
	}

	.project-card:hover .project-image img {
		transform: scale(1.05);
	}

	.project-content {
		padding: 1.5rem;
	}

	.project-title {
		font-size: 1.25rem;
		font-weight: 600;
		color: #1f2937;
		margin-bottom: 0.5rem;
	}

	.project-description {
		color: #64748b;
		line-height: 1.6;
	}
</style>

