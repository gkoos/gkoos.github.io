<script>
	import Job from '$lib/components/job.svelte';
	import Arrow from '$lib/components/arrow.svelte';

	const jobs = [
		{
			time: '2024 - 2025',
			company: 'dmg media (Daily Mail)',
			link: 'https://www.dailymail.co.uk',
			title: 'Senior Software Engineer',
			description: `
        Maintain and improve the company's proprietary Real Time Analytics solution. Record and save every user interaction on every Daily Mail website and banner ad, and present them in a meaningful way in customisable charts and pivot tables etc. via a dashboard app to Operations and Editorial. Feed all the data to a ML solution.
        Design, implement and optimise features in RESTful APIs and gRPC services for seamless communication with microservices and external services.
      `,
			techStack: [
				'Microservices',
				'Typescript',
				'Node.js',
				'Golang',
				'MySQL',
				'Elasticsearch',
				'Redis',
				'Kafka',
				'gRPC',
				'REST',
				'AWS',
				'GCP',
				'Docker',
				'Kubernetes',
				'CI/CD'
			]
		},
		{
			time: 'May 2022 - 2024',
			company: 'Capgemini Invent',
			link: 'https://www.capgemini.com/gb-en/service/invent/',
			title: 'Senior Consultant, People Manager',
			description: `
        Collaborate closely with clients across diverse projects to thoroughly understand their business goals and technical challenges. Engage in detailed discussions to define problem specifications, translate requirements into scalable system architectures, and lead the design and implementation of effective, maintainable solutions tailored to each client's unique context.
      `,
			techStack: [
				'Typescript',
				'Javascript',
				'Node.js',
				'React',
				'Next.js',
				'Redux',
				'Redux Toolkit',
				'Recoil',
				'Electron',
				'Golang',
				'Vercel',
				'Netlify',
				'Redis',
				'MongoDB',
				'DynamoDB',
				'MySQL',
				'Postgres',
				'REST',
				'GraphQL',
				'AWS',
				'GCP',
				'Azure',
				'Contentful',
				'Docker',
				'Kubernetes',
				'Terraform',
				'CI/CD'
			]
		},
		{
			time: 'Jan - Apr 2022',
			company: 'Hedgeflows',
			link: 'https://www.hedgeflows.com/',
			title: 'Senior Full Stack Developer',
			description: `
        Develop a SaaS platform in a team for effectively handling invoices in foreign currencies. Design and implement a robust backend system using Node.js and Google Cloud Functions, ensuring high performance and scalability. Create a user-friendly frontend with React, enhancing the overall user experience.
      `,
			techStack: [
				'Javascript',
				'Node.js',
				'React',
				'Redux',
				'Redux Toolkit',
				'REST',
				'GCP',
				'CI/CD'
			]
		},
		{
			time: '2020 - 2022',
			company: 'Ascential',
			link: 'https://www.ascential.com/',
			title: 'Senior Full Stack Engineer',
			description: `
        Develop, maintain and extend the company's payment platform, called YAP. Integrate new payment service providers and implement new payment methods for existing PSP's. 
        Ensure PCI compliance, make changes to the payment flow according to legal requirements (3DS, SCA, etc.)
        Manage upstream and downstream dependencies, assist the various organisations within the company with their custom requirements and payment related queries
      `,
			techStack: ['Javascript', 'Node.js', 'React', 'MySQL', 'Redis', 'AWS', 'CI/CD', 'Kibana']
		},
		{
			time: 'Jun - Nov 2019',
			company: 'Deko Pay',
			link: 'https://www.dekopay.com/',
			title: 'Senior Software Engineer, Team Lead',
			description: `
        Tech lead for a team of 5 developers.
        Develop the company's rolling credit product in typescript (Node backend, React frontend) following BDD and DDD methodology, integrate it with various e-commerce platforms.
        Do migrations and maintenance work on the company's legacy PHP platform.
      `,
			techStack: [
				'Javascript',
				'Typescript',
				'Node.js',
				'Express',
				'Postgres',
				'MongoDB',
				'React',
				'AWS',
				'PHP',
				'Symfony',
				'CI/CD',
				'Docker',
				'Kubernetes'
			]
		},
		{
			time: 'Jan 2018 - Jun 2019',
			company: 'Betsson Group, London',
			link: 'https://www.betsson.com/en',
			title: 'Senior Software Engineer',
			description: `
        Rewrite the monolithic Drupal application serving supercasino.com, jackpot247.com and vernons.com in a microservice architecture with Angular in the frontend and Node.js and some php in the backend.
        Implement GDPR with Playtech and Betsson's own backend solution called Techsson.
        Internal / admin pages frontend with React.
        Maintenance and bug fixing in Drupal.
      `,
			techStack: [
				'Microservices',
				'PHP',
				'Drupal',
				'Laravel',
				'Javascript',
				'Typescript',
				'Node.js',
				'Express',
				'React',
				'MongoDB',
				'ETCD',
				'AWS',
				'Docker'
			]
		},
		{
			time: 'Jun 2014 - Jan 2018',
			company: 'Racing Post',
			link: 'https://www.racingpost.com/',
			title: 'Software Engineer',
			description: `
        Work on a variety of development projects and delivering solutions to external and internal clients.
        Assist in maintaining the company's Sybase stored procedure codebase.
        Alter the Zend Engine core C code to effectively handle multiple Sybase database connections.
        Software development for terminals in betting shops. Display in an embedded (Chrome based) browser, written in Angular1.4 (some parts in typescript).
      `,
			techStack: [
				'PHP',
				'Zend Framework',
				'C',
				'Phalcon',
				'Sybase',
				'Oracle',
				'Javascript',
				'Angular',
				'jQuery',
				'D3',
				'Redis',
				'RabbitMQ',
				'Vagrant'
			]
		},
		{
			time: 'Oct 2013 - Jun 2014',
			company: 'Goldato Handels GmbH (Munich, Budapest)',
			link: 'https://goldato.com/',
			title: 'Lead Developer',
			description: `
        Lead a small team of developers working on the gold trading platform of the company. Handle concurrency to accurately and effectively calculate rates, commissions etc.
      `,
			techStack: ['PHP', 'Javascript', 'Node.js', 'Express', 'MongoDB']
		},
		{
			time: 'Jul - Oct 2013',
			company: 'AionHill (Budapest)',
			link: 'https://aionhill.com/',
			title: 'Senior Software Developer',
			description: `
        Build and integrate a test automation framework into the company's development workflow (unit, functional and end to end tests).
        Magento development.
      `,
			techStack: ['PHP', 'Magento', 'Javascript', 'Selenium']
		},
		{
			time: 'March 2012 - Jun 2013',
			company: 'Origo (Budapest)',
			link: 'https://origo.hu/',
			title: 'Software Developer',
			description: `
         Develop mobile applications, work on various backend projects (database migration from Oracle to MySQL, introducing nosql solutions like Redis, Memcached and MongoDB) for Origo, the biggest online portal in Hungary.
      `,
			techStack: ['PHP', 'MySQL', 'Oracle', 'Redis', 'MongoDB', 'Memcached']
		}
	];
</script>

<section id="experience" class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24">
	<div
		class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0"
	>
		<h2 class="text-sm font-bold tracking-widest text-slate-200 uppercase">Experience</h2>
	</div>
	<div>
		<ol class="group/list">
			{#each jobs as job}
				<li class="mb-12">
					<Job
						time={job.time}
						company={job.company}
						link={job.link}
						title={job.title}
						description={job.description}
						skills={job.techStack}
					/>
				</li>
			{/each}
		</ol>
		<div class="mt-12">
			<a
				class="group/link inline-flex items-baseline text-base leading-tight font-medium font-semibold text-slate-200 text-slate-200 hover:text-teal-300 focus-visible:text-teal-300"
				href="Gabor_Koos_resume.pdf"
				target="_blank"
				rel="noreferrer noopener"
				aria-label="View Full Résumé (opens in a new tab)"
				><span
					>Download
					<span class="inline-block">Résumé<Arrow /></span></span
				></a
			>
		</div>
	</div>
</section>
