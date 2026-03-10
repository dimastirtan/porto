<script>
	import favicon from '$lib/assets/favicon.ico';
	import logo from '$lib/assets/logo.png';

	let { children } = $props();
	
	let mobileMenuOpen = $state(false);
	
	function toggleMenu() {
		mobileMenuOpen = !mobileMenuOpen;
	}
	
	function closeMenu() {
		mobileMenuOpen = false;
	}
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>Dimas</title>
</svelte:head>

<div class="page-wrapper">
	<header class="navbar">
		<div class="nav-container">
			<a href="/" class="logo" onclick={closeMenu}><img src={logo} alt="Logo" /><span><i>imas</i></span></a>
			
			<!-- Desktop Navigation -->
			<nav class="desktop-nav">
				<a href="#home">Home</a>
				<a href="#about">About</a>
				<a href="#projects">Projects</a>
				<a href="#faqs">FAQs</a>
				<a href="#contact">Contact</a>
			</nav>
			
			<!-- Mobile Menu Button -->
			<button class="mobile-toggle" onclick={toggleMenu} aria-label="Toggle menu">
				<span class="hamburger" class:open={mobileMenuOpen}></span>
			</button>
		</div>
		
		<!-- Mobile Navigation -->
		<nav class="mobile-nav" class:open={mobileMenuOpen}>
			<a href="#home" onclick={closeMenu}>Home</a>
			<a href="#about" onclick={closeMenu}>About</a>
			<a href="#projects" onclick={closeMenu}>Projects</a>
			<a href="#faqs" onclick={closeMenu}>FAQs</a>
			<a href="#contact" onclick={closeMenu}>Contact</a>
		</nav>
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
		scroll-behavior: smooth;
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
		display: inline-flex;
		align-items: center;
		text-decoration: none;
	}

	.logo span {
		font-size: 1.75rem;
		font-weight: 700;
		color: #333;
		font-family: cursive;
	}

	/* Desktop Navigation */
	.desktop-nav {
		display: flex;
		gap: 2rem;
	}

	.desktop-nav a {
		text-decoration: none;
		color: #555;
		font-weight: 500;
		transition: color 0.3s ease;
	}

	.desktop-nav a:hover {
		color: #FF5A5A;
	}

	/* Mobile Toggle Button */
	.mobile-toggle {
		display: none;
		background: none;
		border: none;
		cursor: pointer;
		padding: 0.5rem;
		z-index: 1001;
	}

	.hamburger {
		display: block;
		width: 24px;
		height: 2px;
		background: #333;
		position: relative;
		transition: background 0.3s ease;
	}

	.hamburger::before,
	.hamburger::after {
		content: '';
		position: absolute;
		width: 24px;
		height: 2px;
		background: #333;
		left: 0;
		transition: all 0.3s ease;
	}

	.hamburger::before {
		top: -8px;
	}

	.hamburger::after {
		top: 8px;
	}

	.hamburger.open {
		background: transparent;
	}

	.hamburger.open::before {
		top: 0;
		transform: rotate(45deg);
	}

	.hamburger.open::after {
		top: 0;
		transform: rotate(-45deg);
	}

	/* Mobile Navigation */
	.mobile-nav {
		display: none;
		flex-direction: column;
		background: rgba(255, 255, 255, 0.98);
		gap: 1rem;
		max-height: 0;
		overflow: hidden;
		transition: max-height 0.3s ease, padding 0.3s ease;
	}

	.mobile-nav.open {
		max-height: 320px;
		padding: 1rem 2rem 2rem;
	}

	.mobile-nav a {
		text-decoration: none;
		color: #555;
		font-weight: 500;
		font-size: 1.1rem;
		padding: 0.5rem 0;
		border-bottom: 1px solid #eee;
		transition: color 0.3s ease;
	}

	.mobile-nav a:hover {
		color: #FF5A5A;
	}

	main {
		flex: 1;
		margin-top: 70px;
	}

	/* Responsive Styles */
	@media (max-width: 768px) {
		.desktop-nav {
			display: none;
		}

		.mobile-toggle {
			display: block;
		}

		.mobile-nav {
			display: flex;
		}

		.nav-container {
			padding: 1rem;
		}
	}
</style>

