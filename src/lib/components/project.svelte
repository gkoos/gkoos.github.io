<script>
	import Techcard from '$lib/components/Techcard.svelte';
	import Arrow from '$lib/components/arrow.svelte';

	let { time, title, company, link, description, techs, img } = $props();
</script>

<div
	class="group relative grid pb-1 transition-all sm:grid-cols-8 sm:gap-8 md:gap-4 lg:group-hover/list:opacity-50 lg:hover:!opacity-100"
>
	<div
		class="absolute -inset-x-4 -inset-y-4 z-0 hidden rounded-md transition motion-reduce:transition-none lg:-inset-x-6 lg:block lg:group-hover:bg-slate-800/50 lg:group-hover:shadow-[inset_0_1px_0_0_rgba(148,163,184,0.1)] lg:group-hover:drop-shadow-lg"
	></div>
	<header
		class="z-10 mt-1 mb-2 text-xs font-semibold tracking-wide text-slate-500 uppercase sm:col-span-2"
		aria-label={time}
	>
		{time}
	</header>
	<div class="z-10 sm:col-span-6">
		<h3 class="leading-snug font-medium text-slate-200">
			<div>
				<a
					class="group/link inline-flex items-baseline text-base leading-tight font-medium text-slate-200 hover:text-teal-300 focus-visible:text-teal-300"
					href={link}
					target="_blank"
					rel="noreferrer noopener"
					aria-label="{title} (opens in a new tab)"
				>
					<span
						class="absolute -inset-x-4 -inset-y-2.5 hidden rounded md:-inset-x-6 md:-inset-y-4 lg:block"
					></span>
					<span
						>{title} {#if company}·{/if}
						<span class="inline-block">
							{company}
							<Arrow />
						</span>
					</span>
				</a>
			</div>
		</h3>
    <img src={img} alt={title} class="rounded-md" />
		<p class="mt-2 text-sm leading-normal whitespace-pre-line">
			{description}
		</p>
		<ul class="mt-2 flex flex-wrap" aria-label="Technologies used">
			{#each techs as tech}
				<Techcard label={tech} />
			{/each}
		</ul>
	</div>
</div>
