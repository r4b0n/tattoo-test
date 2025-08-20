<script>
	export let item;
	export let stepsContainer = null;
</script>

<picture
	class="-mx-4 mb-8 aspect-video h-auto w-[calc(100%+2rem)] flex-shrink-0 lg:mx-0 lg:mb-0 lg:w-[32%] xl:-ml-0"
>
	<source srcset={item.image} type="image/webp" />
	<img
		src={item.image}
		alt="{item.label} process illustration"
		class="aspect-video h-auto w-full object-cover lg:rounded-[0.4rem]"
		loading="eager"
		decoding="async"
	/>
</picture>
<div class="order-1 flex-1 lg:order-0 lg:w-[68%] lg:min-w-0">
	<h2 class="text-fluid-h2-secondary mb-6 text-primary lg:text-2xl lg:whitespace-nowrap">
		{item.label}
	</h2>
	<p class="max-w-[350px] font-light">{item.description}</p>
</div>
<ul
	aria-label="Process steps for {item.label}"
	bind:this={stepsContainer}
	class="relative order-2 mt-[9rem] mb-8 flex w-full flex-col gap-6 text-white lg:order-0 lg:mt-4 lg:flex-row xl:px-0"
>
	{#each item.steps as step}
		<li class="flex-1">
			<h3 class="font-gt-america-mono font-medium">{step.title}</h3>
			<hr class="mt-3 mb-6 opacity-50" role="presentation" />
			<p class="text-xs leading-[1.5em] font-light uppercase">{step.description}</p>
		</li>
	{/each}
</ul>
