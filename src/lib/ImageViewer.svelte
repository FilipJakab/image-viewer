<svelte:options customElement="image-viewer"></svelte:options>

<script>
	import PhotoViewer from "photoviewer"
	import "photoviewer/_index.scss"

	export let imageSrc
	export let imageTitle = ""

	// define options (if needed)
	export let options = {};

	let rootElement
	let photoviewer

	$: imageSrc_ = imageSrc || $$props["image-src"]
	$: imageTitle_ = imageTitle || $$props["image-title"]

	function onPreviewImage() {
		if (!rootElement) {
			console.warn("Cannot preview image because rootElement is missing")
			return
		}

		// Initialize the plugin
		photoviewer = new PhotoViewer([{src: imageSrc_, title: imageTitle_}], {
			...options,
			appendTo: rootElement
		});
	}
</script>

<div bind:this={rootElement} class="image-viewer-parent">
	<div class="image-viewer" on:click={onPreviewImage}>
		<img src={imageSrc_}>
	</div>
</div>

<style lang="scss">
	@use 'photoviewer';

	.image-viewer-parent {
		.image-viewer {
			display: flex;
			justify-content: center;
			align-items: center;

			padding: .5rem;
			border-radius: .25rem;
			border: 1px solid;
			min-height: 10rem;
		}
	}
</style>
