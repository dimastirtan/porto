<script>
	import favicon from '$lib/assets/favicon.ico';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Dimas</title>
</svelte:head>

<div class="page-wrapper">
	<header class="navbar">
		<div class="nav-container">
			<a href="/" class="logo">-//-</a>
			<nav>
				<a href="#home">Home</a>
				<a href="#about">About</a>
				<a href="#projects">Projects</a>
				<a href="#contact">Contact</a>
			</nav>
		</div>
	</header>

	<main>
		{@render children()}
	</main>
</div>

<style>
	:global(*) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		scrollbar-width: none;
	}

	:global(body) {
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
		line-height: 1.6;
		color: #333;
		background-color: #fafafa;
	}

	.page-wrapper {
		min-height: 100vh;
		display: flex;
		flex-direction: column;
	}

	.navbar {
		position: fixed;
		top: 0;
		left: 0;
		right: 0;
		background: rgba(255, 255, 255, 0.95);
		backdrop-filter: blur(10px);
		box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
		z-index: 1000;
	}

	.nav-container {
		max-width: 1200px;
		margin: 0 auto;
		padding: 1rem 2rem;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.logo {
		font-size: 1.5rem;
		font-weight: 700;
		text-decoration: none;
		color: #333;
	}

	nav {
		display: flex;
		gap: 2rem;
	}

	nav a {
		text-decoration: none;
		color: #555;
		font-weight: 500;
		transition: color 0.3s ease;
	}

	nav a:hover {
		color: #2563eb;
	}

	main {
		flex: 1;
		margin-top: 70px;
	}
</style>

