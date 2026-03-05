<script>
	let { 
		footerText = '',
		socialLinks = [],
		children 
	} = $props();
</script>

<footer class="site-footer">
	<div class="footer-content">
		{#if footerText}
			<p class="footer-text">{footerText}</p>
		{/if}
		{#if socialLinks && socialLinks.length > 0}
			<div class="social-links">
				{#each socialLinks as link}
					<a href={link.url} target="_blank" rel="noopener noreferrer" class="social-link">
						{link.name}
					</a>
				{/each}
			</div>
		{/if}
		{#if children}
			<div class="footer-extras">
				{@render children()}
			</div>
		{/if}
	</div>
</footer>

<style>
	.site-footer {
		background: #1f2937;
		color: #e5e7eb;
		padding: 3rem 2rem;
		margin-top: auto;
	}

	.footer-content {
		max-width: 1200px;
		margin: 0 auto;
		text-align: center;
	}

	.footer-text {
		font-size: 1rem;
		margin-bottom: 1.5rem;
	}

	.social-links {
		display: flex;
		gap: 1.5rem;
		justify-content: center;
		flex-wrap: wrap;
	}

	.social-link {
		color: #9ca3af;
		text-decoration: none;
		font-weight: 500;
		transition: color 0.3s ease;
	}

	.social-link:hover {
		color: #fff;
	}

	.footer-extras {
		margin-top: 1.5rem;
	}
</style>

