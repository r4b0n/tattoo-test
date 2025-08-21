<script>
	import imgDiscover from '$lib/assets/img_gsd_discover.webp';
	import Button from '$lib/components/ui/Button.svelte';
</script>

<section
	class="relative flex w-full flex-col items-center justify-center"
	aria-label="Discover our work areas"
>
	<article class="grid place-items-center" aria-labelledby="discover-heading">
		<div class="col-start-1 row-start-1 h-auto w-full overflow-hidden">
			<picture>
				<source srcset={imgDiscover} type="image/webp" />
				<img
					src={imgDiscover}
					alt="Areas where we work - showing our global presence"
					class="ml-[-15%] h-full w-full min-w-[1200px] object-cover md:ml-0 md:min-w-[1400px]"
					loading="eager"
					decoding="async"
					role="presentation"
				/>
			</picture>
		</div>
		<div
			class="z-50 col-start-1 row-start-1 flex w-full max-w-[var(--max-width-container-custom)] items-center justify-center px-4 md:justify-start xl:px-0"
			role="main"
		>
			<div class="max-w-[440px]">
				<h1 id="discover-heading" class="text-fluid-h1-gsd max-w-[394px] font-gloock text-white">
					Discover areas where we work
				</h1>
				<p class="py-4" aria-describedby="discover-heading">
					Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et massa mi. Aliquam in
					hendrerit urna. Pellentesque sit amet sapien fringilla, mattis ligula consectetur,
					ultrices mauris. Maecenas vitae mattis tellus. Nullam quis imperdiet augue. Vestibulum
					auctor ornare leo, non suscipit magna interdum eu. Curabitur pellentesque nibh nibh, at
					maximus ante fermentum sit amet. Pellentesque commodo lacus at sodales sodales. Quisque
					sagittis orci ut diam condimentum, vel euismod erat placerat.
				</p>
				<Button variant="gsd" aria-label="Navigate to our work locations page">Where we work</Button
				>
			</div>
		</div>
	</article>
</section>
