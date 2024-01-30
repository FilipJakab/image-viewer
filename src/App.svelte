<script>
	import svelteLogo from './assets/svelte.svg'
	import viteLogo from '/vite.svg'
	import ImageViewer from './lib/ImageViewer.svelte'

	const options = {
		// optionName: 'option value'
		// for example:
		index: 0 // this option means you will start at first image
	}
</script>

<main>
	<div>
		<a href="https://vitejs.dev" rel="noreferrer" target="_blank">
			<img alt="Vite Logo" class="logo" src={viteLogo}/>
		</a>
		<a href="https://svelte.dev" rel="noreferrer" target="_blank">
			<img alt="Svelte Logo" class="logo svelte" src={svelteLogo}/>
		</a>
	</div>
	<h5>In-Svelte Image viewer:</h5>

	<div style="width: 50vw; margin: auto">
		<ImageViewer imageSrc="https://picsum.photos/200/300" {options} />
	</div>
</main>

<style>
	.logo {
		height: 6em;
		padding: 1.5em;
		will-change: filter;
		transition: filter 300ms;
	}

	.logo:hover {
		filter: drop-shadow(0 0 2em #646cffaa);
	}

	.logo.svelte:hover {
		filter: drop-shadow(0 0 2em #ff3e00aa);
	}

	.read-the-docs {
		color: #888;
	}
</style>
