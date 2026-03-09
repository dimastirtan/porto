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

<SectionWrapper title="FAQ" id="faqs">
    <div class="faq-content">
        <p>Have a question? Send me a message <a href="#contact">here</a>!</p>
    </div>
</SectionWrapper>

<SectionWrapper title="Contact" id="contact">
	<p style="text-align: center;">Feel free to reach out or just a friendly chat!</p>
	<div class="contact-content">
		<a href="https://www.instagram.com/direct/t/dimastirtan" target="_blank" class="contact-btn">Instagram</a>
        <a href="https://m.me/iyaasd" target="_blank" class="contact-btn">Facebook</a>
        <a href="https://wa.me/+6281297514895" target="_blank" class="contact-btn">WhatsApp</a>
		<a href="http://t.me/dimastirtan" target="_blank" class="contact-btn">Telegram</a>
		<p style="grid-column: span 2;">OR</p>
		<a href="https://tellonym.me/user.14071660" target="_blank" rel="noopener noreferrer" class="tellonym-btn">Ask Anonymously via Tellonym</a>
	</div>
</SectionWrapper>

<Footer footerText="&copy; 2026 Dimas Tirta Nugraha. Developed using SvelteKit">
	<div class="footer-extras">
		<p>Connect with me on social media!</p>
		<div class="social-links">
			<a href="https://www.instagram.com/dimastirtan" target="_blank" rel="noopener noreferrer" class="social-link">Instagram</a>
			<a href="https://www.facebook.com/dimastirtan" target="_blank" rel="noopener noreferrer" class="social-link">Facebook</a>
		</div>
	</div>
	</Footer>

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
		display: grid;
		grid-template-columns: auto auto;
		gap: 5px;
	}

	.contact-content p {
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

    .faq-content {
        text-align: center;
        padding: 2rem 0;
    }

    .tellonym-btn {
		grid-column: span 2;
		display: inline-block;
        padding: 0.75rem 2rem;
        background: #7c3aed;
        color: white;
        text-decoration: none;
        border-radius: 8px;
        font-weight: 500;
        transition: background 0.3s ease;
    }

    .tellonym-btn:hover {
        background: #6d28d9;
    }

    @media (max-width: 600px) {
        .contact-btn {
            width: 100%;
            margin-bottom: 1rem;
        }
        
        .tellonym-btn {
            width: 100%;
        }
    }
</style>

