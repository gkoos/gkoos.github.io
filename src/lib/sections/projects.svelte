<script>
	import Project from '$lib/components/project.svelte';
	import Arrow from '$lib/components/arrow.svelte';

	const projects = [
		{
			time: '2024',
			company: 'dmg media',
			link: 'https://www.dmgmedia.co.uk/',
			title: 'Data sampling for RTA',
			description: `
        Implement a data sampling solution for the Real Time Analytics platform, which collects and processes user interactions on Daily Mail websites and banner ads. The solution is designed to handle high volumes of data while ensuring that the most relevant trends are captured for analysis.
				The sampling solution is built using Typescript and Node.js, and it integrates with the existing Real Time Analytics platform. It uses a combination of statistical techniques and heuristics to select a representative sample of user interactions, which are then processed and stored in a scalable manner.
      `,
			img: 'images/dmg.jpg',
			techStack: [
				'Typescript',
				'ElasticSearch',
				'OAuth2',
				'Node.js',
				'Redis',
				'REST'
			]
		},
		{
			time: '2023',
			company: 'Capgemini',
			link: 'https://www.capgemini.com/gb-en/industries/retail/cornershop/',
			title: 'CornerShop',
			description: `
        AI-enabled store staff solution to help customers find products in a supermarket, using a mobile app and a web dashboard for store staff.
				The app uses AI to understand the user's intent and provide relevant product information, while the dashboard allows store staff to manage customer requests and provide assistance.
      `,
			img: 'images/cornershop.png',
			techStack: [
				'Javascript',
				'React Native',
				'GCP',
				'Firebase',
				'OpenAI API'
			]
		},
		{
			time: '2023',
			company: 'Capgemini',
			link: 'https://www.frog.co/work/leaping-into-decentralized-conservation',
			title: 'Quest for Hope',
			description: `
        Develop a game on Roblox to raise awareness of the plight of endangered species and the importance of conservation.
      `,
			img: 'images/questforhope.png',
			techStack: [
				'Javascript',
				'Roblox Studio'
			]
		},
		{
			time: '2022',
			company: 'Capgemini',
			link: 'https://www.bp.com/en_gb/united-kingdom/home/news/press-releases/bp-trials-first-uk-self-service-checkout-for-fuel-payment.html',
			title: 'BP self-service order and payment',
			description: `
        Create a proof of concept Electron app to order and pay for food, fuel and car wash, running on proprietary hardware for BP.
      `,
			img: 'images/bp.jpg',
			techStack: [
				'Typescript',
				'React',
				'Redux',
				'Electron',
			]
		},
		{
			time: '2020 - 2021',
			company: 'Ascential',
			link: 'https://www.canneslions.com/pass-picker',
			title: 'Cannes Lions membership / payments',
			description: `
        Integrated payment solution for every Cannes Lions product.
      `,
			img: 'images/canneslions.jpg',
			techStack: [
				'Typescript',
				'Node.js',
				'Express',
				'React',
				'MySQL',
				'Elasticsearch',
				'Redis',
				'AWS'
			]
		},
		{
			time: '2018',
			company: 'Ascential',
			link: 'https://jackpot247.com',
			title: 'Netplay backend',
			description: `
        Complete rewrite of the Netplay casino sites (supercasino.com, jackpot247.com, vernons.com) in a microservices architecture from a monolithic Drupal application.
				GDPR implementation.
				Playtech and Betsson integration.
      `,
			img: 'images/netplay.jpg',
			techStack: [
				'Typescript',
				'Node.js',
				'Koa',
				'Angular',
				'MySQL',
				'ETCD',
				'Docker Swarm',
				'PHP',
				'Drupal',
				'Laravel'
			]
		},
		{
			time: '2017',
			company: 'Racing Post',
			link: 'https://5star.media/2016/12/12/racing-post-best-gaming-technology-launch-exclusive-product/',
			title: 'Integration in BGT betting terminals',
			description: `
       	Enable proprietary Racing Post content on 12000+ self-service betting terminals within multiple UK operator retail betting estates - responsible for the backend and some frontend work.
				Implementation of some Racing Post API calls, full intergation with the RP B2B API.
				Horse and greyhounds race predictor and some of the bet prompts on the frontend.
      `,
			img: 'images/bgt.jpg',
			techStack: [
				'Javascript',
				'Angular',
				'Sybase',
				'PHP',
				'Zend Framework'
			]
		},
		{
			time: '2015 - 2016',
			company: 'Racing Post',
			link: 'https://www.racingpost.com',
			title: 'Reports and feeds for B2B and website',
			description: `
       	Rewrite of Racing Post's legacy content delivery system in a scalable, distributed way.
				Implement a proprietary monitoring system.
      `,
			img: 'images/rp.jpg',
			techStack: [
				'PHP',
				'Python',
				'Sybase',
				'Redis',
				'RabbitMQ',
				'Javascript',
				'Bash'
			]
		}
	];
</script>

<section id="projects" class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24">
	<div
		class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0"
	>
		<h2 class="text-sm font-bold tracking-widest text-slate-200 uppercase">Featured Projects</h2>
	</div>
	<div>
		<ol class="group/list">
			{#each projects as project}
				<li class="mb-12">
					<Project
						time={project.time}
						title={project.title}
						company={project.company}
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
