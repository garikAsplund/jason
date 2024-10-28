<svelte:head>
    <meta name="description" content="Listen to Toska Bear on podcasts." />
</svelte:head>

<div class="relative h-full w-full bg-black flex justify-center items-center">
	<iframe
		title="Podcasts embed"
		class="absolute inset-0 flex items-center justify-center bg-black/60 mx-auto my-auto px-8"
		scrolling="no"
		src="https://open.spotify.com/embed/playlist/4gQgGa8zrWajoBXk6Daadn"
		data-testid="embed-preview-iframe"
		height="380"
		allow="encrypted-media"
		style="max-width: 800px; width: 100%;"
	></iframe>
</div>
