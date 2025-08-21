<script>
	import Video from '$lib/components/layout/Video.svelte';
	import Process from '$lib/components/layout/Process.svelte';
	import CopyWithImages from '$lib/components/layout/CopyWithImages.svelte';
	import CopyOverImage from '$lib/components/layout/CopyOverImage.svelte';
</script>

<main class="relative w-full bg-dark font-gt-america text-white">
	<Video />
	<Process />
</main>

<main class="relative w-full bg-white font-sf-pro-display text-white">
	<CopyWithImages />
	<CopyOverImage />
</main>
