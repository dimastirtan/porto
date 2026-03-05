<script>
	let { 
		children 
	} = $props();
</script>

<div class="faq-section">
	{@render children()}
</div>

<style>
	.faq-section {
		max-width: 800px;
		margin: 0 auto;
	}
</style>

