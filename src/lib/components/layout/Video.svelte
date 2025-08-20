<script>
	import Button from '$lib/components/ui/Button.svelte';
	import imgVideoBg from '$lib/assets/img_video_bg.webp';
</script>

<div class="relative mx-auto mt-8 w-full max-w-[var(--max-width-container-custom)] lg:mt-16">
	<h1
		class="relative mb-[-10%] px-4 text-white lg:px-1"
		style="font-size: var(--font-size-fluid-h1); font-weight: var(--font-weight-bold); line-height: var(--line-height-fluid-h1); letter-spacing: var(--letter-spacing-tight); text-transform: uppercase;"
	>
		Data-Driven.<br />Performance<br /><span class="text-primary">Proven.</span>
	</h1>
	<div class="grid place-items-center">
		<picture
			class="col-start-1 row-start-1 h-auto w-full"
			aria-label="Video background showing data-driven performance"
			role="img"
		>
			<source srcset={imgVideoBg} type="image/webp" />
			<img
				src={imgVideoBg}
				alt="Video background showing data-driven performance"
				class="h-auto w-full object-cover"
				loading="eager"
				decoding="async"
			/>
		</picture>
		<div class="z-50 col-start-1 row-start-1 flex items-center justify-center">
			<Button
				variant="secondary"
				size="sm"
				aria-label="Play video about data-driven performance"
				aria-describedby="video-description"
			>
				Play</Button
			>
			<div id="video-description" class="sr-only">
				Video showcases data-driven performance metrics and proven results from our digital
				marketing campaigns
			</div>
		</div>
	</div>
	<hr class="mt-8 hidden border-white opacity-50 md:flex" role="presentation" />
</div>
