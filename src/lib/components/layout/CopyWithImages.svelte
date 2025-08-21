<script>
	import imgGSD01 from '$lib/assets/img_gsd_01.webp';
	import imgGSD02 from '$lib/assets/img_gsd_02.webp';
	import imgGSD03 from '$lib/assets/img_gsd_03.webp';
	import imgGSD04 from '$lib/assets/img_gsd_04.webp';

	let items = [
		{
			title: 'Supporting and amplifying local efforts',
			description:
				"Communities know what they need best. GSD seeks to engage in locally-led approaches that amplify our partners' existing efforts. We focus on both preparation and response to promote immediate capacity strengthening and longterm disaster resilience.",
			image01: imgGSD01,
			image02: imgGSD02,
			alt: 'Supporting local efforts',
			aria: {
				headingId: 'section-1-heading',
				mainImageLabel: 'Supporting local efforts',
				secondaryImageLabel: 'Supporting image for local community work',
				secondaryImageAlt: 'Local community work'
			}
		},
		{
			title: 'Building<br/>partnerships',
			description:
				'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et massa mi. Aliquam in hendrerit urna. Pellentesque sit amet sapien fringilla, mattis ligula consectetur, ultrices mauris. Maecenas vitae mattis tellus. Nullam quis imperdiet augue. Vestibulum auctor ornare leo, non suscipit magna interdum eu. Curabitur pellentesque nibh nibh, at maximus ante fermentum sit amet. Pellentesque commodo lacus at sodales sodales. Quisque sagittis orci ut diam condimentum, vel euismod erat placerat.',
			image01: imgGSD03,
			image02: imgGSD04,
			alt: 'Building partnerships',
			aria: {
				headingId: 'section-2-heading',
				mainImageLabel: 'Building partnerships',
				secondaryImageLabel: 'Supporting image for partnership work',
				secondaryImageAlt: 'Building partnerships'
			}
		}
	];
</script>

<section
	class="relative mx-auto my-4 flex w-full max-w-[var(--max-width-container-custom)] flex-col items-center justify-center px-4 text-grey lg:my-22 xl:px-0"
	aria-label="Our work and partnerships"
>
	<article
		class="relative grid w-full grid-cols-[70%_30%] grid-rows-[auto_auto] gap-2 overflow-hidden lg:grid-cols-[50%_35%_15%] lg:grid-rows-[auto] lg:gap-4"
		aria-labelledby={items[0].aria.headingId}
	>
		<div
			class="col-span-2 row-start-2 mt-8 mb-8 flex flex-col items-start justify-center lg:col-span-1 lg:col-start-1 lg:row-start-1 lg:mt-0 lg:mb-0 lg:max-w-[500px]"
			role="main"
		>
			<h1 id={items[0].aria.headingId} class="text-fluid-h1-gsd font-gloock text-blue">
				{items[0].title}
			</h1>
			<p class="mt-6 lg:mt-8" aria-describedby={items[0].aria.headingId}>
				{items[0].description}
			</p>
		</div>
		<div class="col-start-1 row-start-1 flex lg:col-start-2 lg:row-start-1" role="img" aria-labelledby={items[0].aria.headingId}>
			<picture class="w-full">
				<source srcset={items[0].image01} type="image/webp" />
				<img
					src={items[0].image01}
					alt={items[0].alt}
					class="h-full w-full object-cover"
					loading="eager"
					decoding="async"
					role="presentation"
				/>
			</picture>
		</div>
		<div
			class="col-start-2 row-start-1 flex items-start justify-center lg:col-start-3 lg:row-start-1"
			role="img"
			aria-label={items[0].aria.secondaryImageLabel}
		>
			<picture class="w-[85%]">
				<source srcset={items[0].image02} type="image/webp" />
				<img
					src={items[0].image02}
					alt={items[0].aria.secondaryImageAlt}
					class="h-full w-full object-cover"
					loading="eager"
					decoding="async"
					role="presentation"
				/>
			</picture>
		</div>
	</article>
	<article
		class="relative mt-4 grid w-full grid-cols-1 grid-rows-[auto_auto_auto] gap-0 lg:mt-0 lg:grid-cols-[49%_51%] lg:grid-rows-[auto_auto] lg:gap-8"
		aria-labelledby={items[1].aria.headingId}
	>
		<div class="col-start-1 row-start-1 flex flex-col lg:col-start-1 lg:row-span-2" role="img" aria-labelledby={items[1].aria.headingId}>
			<picture class="w-full lg:mt-[-4.2rem] lg:w-[85%]">
				<source srcset={items[1].image01} type="image/webp" />
				<img
					src={items[1].image01}
					alt={items[1].alt}
					class="h-full w-full object-cover"
					loading="eager"
					decoding="async"
					role="presentation"
				/>
			</picture>
		</div>
		<div
			class="col-start-1 row-start-2 mt-10 mb-10 flex flex-col items-start justify-center lg:col-start-2 lg:row-start-1 lg:mt-28 lg:mb-0"
			role="main"
		>
			<h1 id={items[1].aria.headingId} class="text-fluid-h1-gsd font-gloock text-blue">{@html items[1].title}</h1>
			<p class="mt-6 lg:mt-8" aria-describedby={items[1].aria.headingId}>{items[1].description}</p>
		</div>
		<div class="col-start-1 row-start-3 flex lg:col-start-2 lg:row-start-2" role="img" aria-label={items[1].aria.secondaryImageLabel}>
			<picture class="w-full lg:mt-[4rem]">
				<source srcset={items[1].image02} type="image/webp" />
				<img
					src={items[1].image02}
					alt={items[1].aria.secondaryImageAlt}
					class="h-full w-full object-cover"
					loading="eager"
					decoding="async"
					role="presentation"
				/>
			</picture>
		</div>
	</article>
</section>
