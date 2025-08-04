<script>
	import Project from '$lib/components/project.svelte';
	import Arrow from '$lib/components/arrow.svelte';

	const projects = [
		{
			time: '2025-',
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
