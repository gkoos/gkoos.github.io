<script>
	import Testimonial from '$lib/components/testimonial.svelte';

	const testimonials = [
		{
			name: 'Scott Ronan',
			title: 'Head of Technology at Betsson Group',
			img: 'images/scott.jpg',
			text: `
        Whilst I worked with Gabor he demonstrated a strong understanding of web and software development with good attention to detail. Diligent and helpful I would work with him again.
      `
		},
		{
			name: 'Preetam De',
			title: 'Scrum Master/Agile Coach',
			img: 'images/pree.jpg',
			text: `
        Gabor, while working in my Scrum team in Betsson group, emerged as an exceptional developer with vast knowledge to back up his wisdom. Always curious to find out the root cause of issues and business outcome validity. He is very professional and fit right in on any team he works with. He will be a great asset to every team who needs a trusted member to rely on.
      `
		},
    {
			name: 'Paolo Casani',
			title: 'Senior Developer',
			img: 'images/paolo.jpg',
			text: `
        I have had the pleasure to work closely with Gabor while at the Racing Post. He joined a core project that I had been working on for a few months. Immediately, he hit the ground running, taking ownership and developing very sophisticated but neat solutions. Gabor is a really outstanding and very talented developer. At the Racing Post he was well known for completing in a matter of a few hours tasks that took others many days. Having played professional basketball as a younger man, Gabor is of course a very good team player and has a jovial character. I can only strongly recommend him.
      `
		},
    {
			name: 'Robin Doran',
			title: 'Deputy IT Director',
			img: 'images/robin.jpg',
			text: `
        It was a pleasure working with Gabor. He was key member of our development team.
      `
		},
	];
</script>

<section id="testimonials" class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24">
	<div
		class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0"
	>
		<h2 class="text-sm font-bold tracking-widest text-slate-200 uppercase">Testimonials</h2>
	</div>
	<div>
		<ol class="group/list">
			{#each testimonials as testimonial}
				<li class="mb-12">
					<Testimonial
						name={testimonial.name}
            title={testimonial.title}
            img={testimonial.img}
            text={testimonial.text}
					/>
				</li>
			{/each}
		</ol>
	</div>
</section>
