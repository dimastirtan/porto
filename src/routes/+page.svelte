<script>
	import SectionWrapper from '$lib/components/SectionWrapper.svelte';
	import About from '$lib/components/About.svelte';
	import Header from '$lib/components/Header.svelte';
	import Projects from '$lib/components/Projects.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let projects = $state([
		{
			title: 'PDAM Lending App',
			description: 'Web-based vehicle lending application for PDAM Tirta Raharja',
			imageUrl: 'https://fergief.vercel.app/_next/image?url=%2Fpdam.png&w=640&q=75'
		},
		{
			title: 'SPBU Management System',
			description: 'A web-based attendance management system for SPBU Pertamina in 8 spots',
			imageUrl: 'https://fergief.vercel.app/_next/image?url=%2Fspbu.png&w=640&q=75'
		},
		{
			title: 'Rich Music',
			description: 'A web-based music article platform by Rich Music',
			imageUrl: 'https://fergief.vercel.app/_next/image?url=%2Frichmusic.png&w=640&q=75'
		}
	]);

	let faqs = $state([
		{
			question: 'What services do you offer?',
			answer: 'I specialize in full-stack web development, including SvelteKit, React, Node.js, and modern UI/UX design.'
		},
		{
			question: 'How can we get started?',
			answer: 'Send me a message via WhatsApp, email, or social media to discuss your project requirements and timeline.'
		}
	]);
</script>

<Header 
	name="Dimas Tirta Nugraha" 
	shortDescription="Tech Enthusiast and Developer"
/>

<SectionWrapper title="Greetings" id="about">
	<About 
		title="Hai, Saya Dimas Tirta Nugraha" 
		description="Selamat datang, di website ini kamu bisa mendapat informasi tentang saya, dan beberapa dokumentasi proyek yang telah saya kerjakan, jika ingin menghubungi saya, silahkan menuju ke section 'Contact'"
	/>
</SectionWrapper>

<SectionWrapper title="Projects" id="projects" variant="alt">
	<div class="projects-grid">
		{#each projects as project}
			<Projects 
				title={project.title}
				description={project.description}
				imageUrl={project.imageUrl}
			/>
		{/each}
	</div>
</SectionWrapper>

<SectionWrapper title="FAQ" id="faqs">
    <div class="faq-content">
		<div class="layout">
			{#each faqs as faq}
				<div>
					<h3>{faq.question}</h3>
					<p>{faq.answer}</p>
				</div>
			{/each}
		</div>
        <p>Have a question? Send me a message <a href="#contact">here</a>!</p>
    </div>
</SectionWrapper>

<SectionWrapper title="Contact" id="contact">
	<p class="contact-intro">Feel free to reach out or just a friendly chat!</p>
	<div class="contact-content">
		<a href="https://ig.me/m/dimastirtan" target="_blank" class="contact-btn" rel="noopener noreferrer">Instagram</a>
        <a href="https://m.me/iyaasd" target="_blank" class="contact-btn" rel="noopener noreferrer">Facebook</a>
        <a href="https://wa.me/+6281297514895" target="_blank" class="contact-btn" rel="noopener noreferrer">WhatsApp</a>
		<a href="http://t.me/dimastirtan" target="_blank" class="contact-btn" rel="noopener noreferrer">Telegram</a>
		<p>OR</p>
		<a href="https://tellonym.me/user.14071660" target="_blank" rel="noopener noreferrer" class="tellonym-btn">Ask Anonymously via Tellonym</a>
	</div>
</SectionWrapper>

<Footer footerText="&copy; 2026 Dimas Tirta Nugraha. Developed using SvelteKit">
	<div class="footer-extras">
		<p>Connect with me on social media!</p>
		<div class="social-links">
			<a href="https://www.instagram.com/dimastirtan" target="_blank" rel="noopener noreferrer" class="social-link">Instagram</a>
			<a href="https://www.facebook.com/dimastirtan" target="_blank" rel="noopener noreferrer" class="social-link">Facebook</a>
			<a href="https://wa.me/+6281297514895" target="_blank" class="social-link" rel="noopener noreferrer">WhatsApp</a>
			<a href="http://t.me/dimastirtan" target="_blank" class="social-link" rel="noopener noreferrer">Telegram</a>
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
		display: grid;
		grid-template-columns: auto auto;
		gap: 5px;
		justify-content: center;
	}

	.contact-content p {
		text-align: center;
	}

	.contact-intro {
		text-align: center;
		margin-bottom: 1rem;
	}

	.contact-content p {
		color: #555;
		justify-content: center;
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
        text-align: left;
    }

	.layout {
		display: grid;
		grid-template-columns: 1fr 1fr;
		row-gap: 2rem;
		column-gap: 2rem;
		padding: 2rem;
		width: 100%;
		background: #f3f4f6;
		border-radius: 12px;
		margin-bottom: 1rem;
	}

	.layout h3 {
		font-size: 1.25rem;
		font-weight: 600;
		color: #1f2937;
		margin-bottom: 0.5rem;
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
		.layout{
			grid-template-columns: auto;
		}
    }
</style>

