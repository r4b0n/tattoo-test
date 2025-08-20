<script>
	import Video from '$lib/components/layout/Video.svelte';
	import Process from '$lib/components/layout/Process.svelte';
	import Button from '$lib/components/ui/Button.svelte';
	import CopyWithImages from '$lib/components/layout/CopyWithImages.svelte';
	import imgDiscover from '$lib/assets/img_gsd_discover.webp';
</script>

<main class="relative w-full bg-dark font-gt-america text-white">
	<Video />
	<Process />
</main>

<main class="relative w-full bg-white font-sf-pro-display text-white">
	<CopyWithImages />
	<section class="relative flex w-full flex-col items-center justify-center">
		<div class="grid place-items-center">
			<picture class="col-start-1 row-start-1 h-auto w-full overflow-hidden">
				<source srcset={imgDiscover} type="image/webp" />
				<img
					src={imgDiscover}
					alt="Discover"
					class="ml-[-15%] h-full w-full min-w-[1200px] object-cover md:ml-0 md:min-w-[1400px]"
					loading="eager"
					decoding="async"
				/>
			</picture>
			<div
				class="z-50 col-start-1 row-start-1 flex w-full max-w-[var(--max-width-container-custom)] items-center justify-center px-4 md:justify-start xl:px-0"
			>
				<div class="max-w-[440px]">
					<h1 class="text-fluid-h1-gsd max-w-[400px] font-gloock text-white">
						Discover areas where we work
					</h1>
					<p class="py-4">
						Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut et massa mi. Aliquam in
						hendrerit urna. Pellentesque sit amet sapien fringilla, mattis ligula consectetur,
						ultrices mauris. Maecenas vitae mattis tellus. Nullam quis imperdiet augue. Vestibulum
						auctor ornare leo, non suscipit magna interdum eu. Curabitur pellentesque nibh nibh, at
						maximus ante fermentum sit amet. Pellentesque commodo lacus at sodales sodales. Quisque
						sagittis orci ut diam condimentum, vel euismod erat placerat.
					</p>
					<Button variant="gsd">Where we work</Button>
				</div>
			</div>
		</div>
	</section>
</main>
