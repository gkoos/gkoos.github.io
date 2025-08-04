<script>
	import { onMount } from 'svelte';
	import '../app.css';
	import Menu from '$lib/components/menu.svelte';

	let { children } = $props();

	let menuItems = [
		{ name: 'About Me', href: 'about' },
		{ name: 'Experience', href: 'experience' },
		{ name: 'Featured Projects', href: 'projects' },
		{ name: 'Testimonials', href: 'testimonials' },
		{ name: 'Side Projects', href: 'side-projects' },
		{ name: 'Dev Blog', href: 'https://dev.to/gkoos', external: true },
	];

	onMount(() => {
		const navItems = document.querySelectorAll('menu li.nav-item');
		const sections = document.querySelectorAll('main > section');

		const hash = window.location.hash || '#about';
		const target = document.querySelector(hash);
		target.scrollIntoView({ behavior: 'smooth' });
		navItems.forEach((item) => {
			const link = item.querySelector('a');
			if (link.getAttribute('href') === hash && !link.hasAttribute('target')) {
				item.classList.add('active');
			} else {
				item.classList.remove('active');
			}
		});

		window.addEventListener('scroll', function () {
			const currentPos = window.scrollY;

			sections.forEach(function (section) {
				const sectionTop = section.offsetTop - 300;
				const sectionHeight = section.offsetHeight;
				const sectionId = section.getAttribute('id');

				if (currentPos >= sectionTop && currentPos < sectionTop + sectionHeight) {
					navItems.forEach(function (navItem) {
						navItem.classList.remove('active');
					});

					const targetNavItem = document.querySelector('li.nav-item a[href="#' + sectionId + '"]');
					if (targetNavItem && !targetNavItem.hasAttribute('target')) {
						targetNavItem.parentNode.classList.add('active');
					}
				}
			});
		});
	});
</script>

<div class="mx-auto min-h-screen max-w-screen-xl px-6 py-12 md:px-12 md:py-16 lg:py-0">
	<div class="lg:flex lg:justify-between lg:gap-4">
		<header
			class="lg:sticky lg:top-0 lg:flex lg:max-h-screen lg:w-[48%] lg:flex-col lg:justify-between lg:py-24"
		>
			<div>
				<h1 class="text-4xl font-bold tracking-tight text-slate-200 sm:text-5xl">
					<a href="/">Gabor Koos</a>
				</h1>
				<h2 class="mt-3 text-lg font-medium tracking-tight text-slate-200 sm:text-xl">
					Full Stack / Backend Engineer
				</h2>
				<p class="mt-4 max-w-xs leading-normal">
					I design and build scalable, maintainable, high-performance digital experiences for the
					web.
				</p>

				<Menu items={menuItems}></Menu>
			</div>
			<ul class="mt-8 ml-1 flex items-center" aria-label="Social media">
				<li class="mr-5 shrink-0 text-xs">
					<a
						class="block hover:text-slate-200"
						href="https://github.com/gkoos"
						target="_blank"
						rel="noreferrer noopener"
						aria-label="GitHub (opens in a new tab)"
						title="GitHub"
					>
						<span class="sr-only">GitHub</span>
						<svg
							xmlns="http://www.w3.org/2000/svg"
							viewBox="0 0 16 16"
							fill="currentColor"
							class="h-6 w-6"
							aria-hidden="true"
						>
							<path
								d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"
							></path>
						</svg>
					</a>
				</li>
				<li class="mr-5 shrink-0 text-xs">
					<a
						class="block hover:text-slate-200"
						href="https://www.linkedin.com/in/gabor-koos-317b8a48/"
						target="_blank"
						rel="noreferrer noopener"
						aria-label="LinkedIn (opens in a new tab)"
						title="LinkedIn"
					>
						<span class="sr-only">LinkedIn</span>
						<svg
							xmlns="http://www.w3.org/2000/svg"
							viewBox="0 0 24 24"
							fill="currentColor"
							class="h-6 w-6"
							aria-hidden="true"
						>
							<path
								d="M20.5 2h-17A1.5 1.5 0 002 3.5v17A1.5 1.5 0 003.5 22h17a1.5 1.5 0 001.5-1.5v-17A1.5 1.5 0 0020.5 2zM8 19H5v-9h3zM6.5 8.25A1.75 1.75 0 118.3 6.5a1.78 1.78 0 01-1.8 1.75zM19 19h-3v-4.74c0-1.42-.6-1.93-1.38-1.93A1.74 1.74 0 0013 14.19a.66.66 0 000 .14V19h-3v-9h2.9v1.3a3.11 3.11 0 012.7-1.4c1.55 0 3.36.86 3.36 3.66z"
							></path>
						</svg>
					</a>
				</li>
				<li class="mr-5 shrink-0 text-xs">
					<a
						class="block hover:text-slate-200"
						href="Gabor_Koos_resume.pdf"
						target="_blank"
						rel="noreferrer noopener"
						aria-label="CV in PDF (opens in a new tab)"
						title="LinkedIn"
					>
						<span class="sr-only">CV</span>
						<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 448 512"
							><!-- Icon from Academicons by James Walsh - https://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL --><path
								fill="currentColor"
								d="M48 32C21.5 32 0 53.5 0 80v352c0 26.5 21.5 48 48 48h352c26.5 0 48-21.5 48-48V80c0-26.5-21.5-48-48-48zm98.88 133.234c19.636 0 37.082 6.789 49.929 16.971c11.88 9.452 17.444 18.907 22.298 27.393l-33.923 16.949c-2.427-5.565-5.347-11.387-12.846-17.682c-8.248-6.552-16.478-8.484-23.524-8.484c-27.626 0-42.17 25.693-42.17 54.287c0 37.573 19.161 56.22 42.17 56.22c22.3 0 31.278-15.51 37.08-25.435L219.6 302.66c-6.315 9.926-12.374 19.635-25.95 29.069c-7.262 5.09-23.977 15.037-47.736 15.037C100.586 346.766 64 313.81 64 255.87c0-50.636 34.415-90.637 82.88-90.637m75.483 5.328h45.565L303.31 292.24l35.125-121.678H384l-59.379 171.112H281.01z"
							/></svg
						>
					</a>
				</li>
			</ul>
		</header>
		<main id="content" class="pt-24 lg:w-[52%] lg:py-24">
			{@render children()}
		</main>
	</div>
</div>
