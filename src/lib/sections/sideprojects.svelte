<script>
	import Project from '$lib/components/project.svelte';
	import Arrow from '$lib/components/arrow.svelte';

	const projects = [
		{
			time: '2025-',
			company: 'Ffetch',
			link: 'https://github.com/gkoos/ffetch',
			title: 'Ffetch',
					description: `
						A production-ready, TypeScript-first library that serves as a drop-in replacement for the native fetch, offering all available options and full flexibility.
						It supports advanced request/response manipulation, interceptors, retries, delays, hooks, and custom errors.
					`,
			img: 'images/npm.jpg',
			techStack: [
				'TypeScript',
			]
		},
		{
			time: '2025-',
			company: 'Nullmail',
			link: 'https://nullmail.cc',
			title: 'Nullmail',
			description: `
        Nullmail is a privacy-focused, ephemeral tempmail service built with SvelteKit, Supabase, and ForwardEmail, hosted on Vercel. 
				It provides instant, disposable inboxes with automatic expiry, no sign-up, and no tracking. Ideal for quick, anonymous email verification and sign-up flows.
				Github: https://github.com/gkoos/nullmail
      `,
			img: 'images/nullmail.jpg',
			techStack: [
				'JavaScript',
				'SvelteKit',
				'Vercel',
				'Supabase',
				'Cloudflare'
			]
		},
		{
			time: '2024-',
			company: 'Skyline',
			link: 'https://github.com/gkoos/skyline',
			title: 'A Go library for skyline queries',
			description: `
        Multi-dimensional optimization to find the set of Pareto-optimal points from a dataset.
        Supports both static and dynamic skyline computation with multiple algorithms and partial queries.
      `,
			img: 'images/skyline.svg',
			techStack: [
				'Golang',
			]
		},
	];
</script>

<section id="side-projects" class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24">
	<div
		class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0"
	>
		<h2 class="text-sm font-bold tracking-widest text-slate-200 uppercase">Side Projects</h2>
	</div>
	<div>
		<ol class="group/list">
			{#each projects as project}
				<li class="mb-12">
					<Project
						time={project.time}
						title={project.title}
						link={project.link}
						img={project.img}
						description={project.description}
						techs={project.techStack}
					/>
				</li>
			{/each}
		</ol>
	</div>
</section>
