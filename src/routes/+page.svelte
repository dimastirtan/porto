<script>
	import SectionWrapper from '$lib/components/SectionWrapper.svelte';
	import About from '$lib/components/About.svelte';
	import Header from '$lib/components/Header.svelte';
	import Projects from '$lib/components/Projects.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<Header 
	name="Dimas Tirta Nugraha" 
	shortDescription="Tech Enthusiast and Developer"
/>

<SectionWrapper title="About Me" id="about">
	<About 
		title="About Me" 
		description="Person who interest in techs."
	/>
</SectionWrapper>

<SectionWrapper title="Projects" id="projects" variant="alt">
	<div class="projects-grid">
		<Projects 
			title="PDAM Lending App"
			description="Web-based vehicle lending application for PDAM Tirta Raharja"
			imageUrl="https://fergief.vercel.app/_next/image?url=%2Fpdam.png&w=640&q=75"
		/>
		<Projects 
			title="SPBU Management System"
			description="A web-based attendance management system for SPBU Pertamina in 8 spots"
			imageUrl="https://fergief.vercel.app/_next/image?url=%2Fspbu.png&w=640&q=75"
		/>
		<Projects 
			title="Rich Music"
			description="A web-based music article platform by Rich Music"
			imageUrl="https://fergief.vercel.app/_next/image?url=%2Frichmusic.png&w=640&q=75"
		/>
	</div>
</SectionWrapper>

<SectionWrapper title="Contact" id="contact">
	<div class="contact-content">
		<p>Feel free to reach out or just a friendly chat!</p>
		<a href="https://www.instagram.com/direct/t/dimastirtan" class="contact-btn">Instagram</a>
        <a href="https://m.me/iyaasd" class="contact-btn">Facebook</a>
        <a href="https://wa.me/+6281297514895" class="contact-btn">WhatsApp</a>
	</div>
</SectionWrapper>

<Footer footerText="&copy; 2026 Dimas Tirta Nugraha. Developed using SvelteKit" />

<style>
	.projects-grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 2rem;
		padding: 1rem 0;
	}

	.contact-content {
		text-align: center;
		padding: 2rem 0;
	}

	.contact-content p {
		margin-bottom: 1.5rem;
		color: #555;
	}

	.contact-btn {
		display: inline-block;
		padding: 0.75rem 2rem;
		background: #2563eb;
		color: white;
		text-decoration: none;
		border-radius: 8px;
		font-weight: 500;
		transition: background 0.3s ease;
	}

	.contact-btn:hover {
		background: #1d4ed8;
	}

    @media (max-width: 600px) {
        .contact-btn {
            width: 100%;
            margin-bottom: 1rem;
        }
    }
</style>

