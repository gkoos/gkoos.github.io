<script>
	let { items } = $props();
</script>

<nav class="nav hidden lg:block" aria-label="In-page jump links">
	<menu class="mt-16 w-max" id="nav-menu">
		{#each items as item}
			<li class="nav-item">
				{#if item.external}
					<a class="group flex items-center py-3" href={item.href} target="_blank" rel="noreferrer noopener">
						<span
							class="nav-indicator mr-4 h-px w-8 bg-slate-600 transition-all group-hover:w-16 group-hover:bg-slate-200 group-focus-visible:w-16 group-focus-visible:bg-slate-200 motion-reduce:transition-none"
						></span>
						<span
							class="nav-text text-xs font-bold tracking-widest text-slate-500 uppercase group-hover:text-slate-200 group-focus-visible:text-slate-200"
							>{item.name}</span
						>
					</a>
				{:else}
					<a class="group flex items-center py-3" href="#{item.href}">
						<span
							class="nav-indicator mr-4 h-px w-8 bg-slate-600 transition-all group-hover:w-16 group-hover:bg-slate-200 group-focus-visible:w-16 group-focus-visible:bg-slate-200 motion-reduce:transition-none"
						></span>
						<span
							class="nav-text text-xs font-bold tracking-widest text-slate-500 uppercase group-hover:text-slate-200 group-focus-visible:text-slate-200"
							>{item.name}</span
						>
					</a>
				{/if}
			</li>
		{/each}
	</menu>
</nav>
