<script>
	import Button from '$lib/components/ui/Button.svelte';
	import ProcessItem from '$lib/components/layout/ProcessItem.svelte';
	import { onMount } from 'svelte';
	import imgStrategy from '$lib/assets/img_strategy.webp';
	import imgDesign from '$lib/assets/img_design.webp';
	import imgDevelopment from '$lib/assets/img_dev.webp';
	import imgResults from '$lib/assets/img_results.webp';

	let stepsContainer;
	let navElement;
	let dynamicMargin = '-32rem';
	let containerPadding = '0px';

	let processItems = [
		{
			label: 'Strategy',
			size: 'md',
			active: true,
			image: imgStrategy,
			description:
				'At Tattoo Digital, there is no fake hustle. Every project starts with a plan, informed by an in-depth discovery and built on strategy.',
			steps: [
				{
					title: '01. Research',
					description:
						'We analyze target audiences and define the platform and technical requirements by leveraging UX strategy and content needs.'
				},
				{
					title: '02. UX Strategy',
					description:
						'After discovery, we begin applying your business model and consumer persona ideas as we craft the user journey on your site.'
				},
				{
					title: '03. Planning',
					description: "We define your website's architecture, features, and content needs."
				}
			]
		},
		{
			label: 'Design',
			size: 'lg',
			active: false,
			image: imgDesign,
			description:
				'We create beautiful, functional designs that align with your brand strategy and deliver exceptional user experiences.',
			steps: [
				{
					title: '01. Wireframing',
					description:
						'We translate strategy into low-fidelity layouts to visualize structure, hierarchy, and flow before adding detail.'
				},
				{
					title: '02. Visual Design',
					description:
						'Our designers craft modern, engaging interfaces that capture your brand identity while emphasizing usability.'
				},
				{
					title: '03. Prototyping',
					description:
						'Interactive prototypes bring designs to life, allowing for feedback and refinement before development begins.'
				}
			]
		},
		{
			label: 'Development',
			size: 'md',
			active: false,
			image: imgDevelopment,
			description:
				'Our development team brings designs to life with clean, scalable code and modern technologies.',
			steps: [
				{
					title: '01. Front-End Development',
					description:
						'We implement responsive, accessible, and performant interfaces to ensure seamless interaction across devices.'
				},
				{
					title: '02. Back-End Development',
					description:
						'Our engineers build scalable architectures, integrating databases, APIs, and business logic securely and efficiently.'
				},
				{
					title: '03. Quality Assurance',
					description:
						'Through rigorous testing, we ensure every feature functions smoothly, delivering a reliable and bug-free experience.'
				}
			]
		},
		{
			label: 'Results',
			size: 'lg',
			active: false,
			image: imgResults,
			description:
				'We measure success through data-driven insights and continuous optimization to ensure your goals are met.',
			steps: [
				{
					title: '01. Analytics Setup',
					description:
						'We implement tracking tools to measure performance, user behavior, and key conversion metrics.'
				},
				{
					title: '02. Performance Review',
					description:
						'Our team evaluates KPIs, gathers insights, and identifies opportunities for improvement based on real data.'
				},
				{
					title: '03. Optimization',
					description:
						'We refine content, design, and functionality through A/B testing and iteration to maximize results.'
				}
			]
		}
	];

	function handleClick(item) {
		processItems = processItems.map((i) => ({
			...i,
			active: i === item
		}));
		// Recalculate margin after state change
		setTimeout(calculateMargin, 50);
	}

	function calculateMargin() {
		if (stepsContainer) {
			const height = stepsContainer.offsetHeight;
			const baseMargin = 150; // 9rem in pixels (assuming 16px base)
			const totalNegativeMargin = -(baseMargin + height);
			// Only apply dynamic margin below lg breakpoint (1024px)
			if (window.innerWidth < 1024) {
				dynamicMargin = `${totalNegativeMargin}px`;
				containerPadding = `${Math.abs(totalNegativeMargin + 100)}px`;
			} else {
				dynamicMargin = '0px';
				containerPadding = '0px';
			}
		}
	}

	onMount(() => {
		calculateMargin();
		// Recalculate on window resize
		const handleResize = () => calculateMargin();
		window.addEventListener('resize', handleResize);

		// Preload all images
		processItems.forEach((item) => {
			const img = new Image();
			img.src = item.image;
		});

		return () => window.removeEventListener('resize', handleResize);
	});
</script>

<div
	class="relative mx-auto mt-6 mb-8 flex w-full max-w-[var(--max-width-container-custom)] flex-col-reverse items-start justify-center px-4 lg:mt-16 lg:mb-16 lg:flex-row xl:px-0"
	style="padding-bottom: {containerPadding};"
	aria-labelledby="process-heading"
>
	<nav
		bind:this={navElement}
		aria-label="Process steps navigation"
		class="z-10 flex w-[100%] flex-col overflow-auto pb-4 lg:mt-0 lg:w-[300px] lg:overflow-hidden lg:pb-0"
		style="margin-top: {dynamicMargin};"
	>
		<header class="mt-7 mb-12 hidden lg:block">
			<p class="text-sm tracking-wide uppercase">• &nbsp; &nbsp; Our Process</p>
		</header>
		<ul class="flex flex-row gap-4 lg:flex-col lg:gap-8" role="tablist">
			{#each processItems as item}
				<li>
					<Button
						role="tab"
						aria-selected={item.active}
						aria-controls="process-content"
						class={item.active ? 'active' : ''}
						variant="primary"
						size={item.size}
						on:click={() => handleClick(item)}>{item.label}</Button
					>
				</li>
			{/each}
		</ul>
	</nav>
	<div class="relative flex w-full flex-col items-start gap-1 lg:flex-row lg:flex-wrap lg:gap-6">
		<h2 id="process-heading" class="text-fluid-h2 order-1 whitespace-nowrap text-white lg:order-0">
			Our Process<span class="inline-block translate-x-[-0.1em] translate-y-[0.12em]">：</span>
		</h2>
		{#each processItems as item}
			{#if item.active}
				<ProcessItem {item} bind:stepsContainer />
			{/if}
		{/each}
	</div>
</div>
