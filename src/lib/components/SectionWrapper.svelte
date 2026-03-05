<script>
	let { 
		title = '', 
		variant = 'default', 
		id = '',
		children 
	} = $props();
</script>

<section class={variant} {id}>
	<div class="section-content">
		{#if title}
			<h2 class="section-title">{title}</h2>
		{/if}
		<div class="section-body">
			{@render children()}
		</div>
	</div>
</section>

<style>
	section {
		padding: 4rem 2rem;
		min-height: 50vh;
	}

	.section-content {
		max-width: 1200px;
		margin: 0 auto;
	}

	.section-title {
		font-size: 2.5rem;
		font-weight: 700;
		margin-bottom: 2rem;
		color: #1f2937;
		position: relative;
	}

	.section-title::after {
		content: '';
		display: block;
		width: 60px;
		height: 4px;
		background: #2563eb;
		margin-top: 0.5rem;
		border-radius: 2px;
	}

	.section-body {
		line-height: 1.8;
	}

	.default {
		background-color: #ffffff;
	}

	.alt {
		background-color: #f8fafc;
	}

	.dark {
		background-color: #1f2937;
		color: #fff;
	}

	.dark .section-title {
		color: #fff;
	}

	.dark .section-title::after {
		background: #60a5fa;
	}
</style>

