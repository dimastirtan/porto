<script>
	let { 
		name = '', 
		shortDescription = '',
		children 
	} = $props();
</script>

<header class="hero" id="home">
	<div class="hero-content">
		<h1 class="name">{name}</h1>
		<p class="tagline">{shortDescription}</p>
		<div class="hero-cta">
			<a href="#projects" class="btn btn-primary">My Work</a>
			<a href="#contact" class="btn btn-outline">Contact</a>
		</div>
		{#if children}
			<div class="hero-extras">
				{@render children()}
			</div>
		{/if}
	</div>
</header>

<style>
	.hero {
		min-height: calc(100vh - 70px);
		display: flex;
		align-items: center;
		justify-content: center;
		text-align: center;
		padding: 2rem;
		background: linear-gradient(135deg, #DDAED3 0%, #6594B1 100%);
	}

	.hero-content {
		max-width: 800px;
	}

	.name {
		font-size: 3.5rem;
		font-weight: 800;
		color: #213C51;
		margin-bottom: 1rem;
		letter-spacing: -0.02em;
	}

	.tagline {
		font-size: 1.5rem;
		color: #213C51;
		margin-bottom: 2rem;
		line-height: 1.6;
	}

	.hero-cta {
		display: flex;
		gap: 1rem;
		justify-content: center;
		flex-wrap: wrap;
	}

	.btn {
		display: inline-block;
		padding: 0.875rem 2rem;
		font-size: 1rem;
		font-weight: 600;
		text-decoration: none;
		border-radius: 8px;
		transition: all 0.3s ease;
		cursor: pointer;
	}

	.btn-primary {
		background: #EEEEEE;
		color: #213C51;
		border: 2px solid #EEEEEE;
	}

	.btn-primary:hover {
		background: #EEEEEE;
		border-color: #213C51;
		transform: translateY(-2px);
		box-shadow: 0 4px 12px rgba(37, 99, 235, 0.3);
	}

	.btn-outline {
		background: transparent;
		color: #EEEEEE;
		border: 2px solid #EEEEEE;
	}

	.btn-outline:hover {
		background: #213C51;
		color: #EEEEEE;
		transform: translateY(-2px);
	}

	.hero-extras {
		margin-top: 2rem;
	}

	@media (max-width: 768px) {
		.name {
			font-size: 2.5rem;
		}
		
		.tagline {
			font-size: 1.25rem;
		}
	}
</style>

