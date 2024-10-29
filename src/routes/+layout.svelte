<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import '../app.css';
	import { page } from '$app/stores';
	import Icons from '$lib/Icons.svelte';
	import Nav from '$lib/Nav.svelte';
	import MobileNav from '$lib/MobileNav.svelte';
	import { dev } from '$app/environment';
	import { inject } from '@vercel/analytics';

	console.log(
    `%c
  ,ad8888ba,                           88  88              ,ad8888ba,                         88                         
 d8"'    \`"8b                          ""  88             d8"'    \`"8b                        88                         
d8'                                        88            d8'                                  88                         
88             ,adPPYYba,  8b,dPPYba,  88  88   ,d8      88              ,adPPYba,    ,adPPYb,88   ,adPPYba,  ,adPPYba,  
88      88888  ""     \`Y8  88P'   "Y8  88  88 ,a8"       88             a8"     "8a  a8"    \`Y88  a8P_____88  I8[    ""  
Y8,        88  ,adPPPPP88  88          88  8888[         Y8,            8b       d8  8b       88  8PP"""""""   \`"Y8ba,   
 Y8a.    .a88  88,    ,88  88          88  88\`"Yba,       Y8a.    .a8P  "8a,   ,a8"  "8a,   ,d88  "8b,   ,aa  aa    ]8I  
  \`"Y88888P"   \`"8bbdP"Y8  88          88  88   \`Y8a       \`"Y8888Y"'    \`"YbbdP"'    \`"8bbdP"Y8   \`"Ybbd8"'  \`"YbbdP"'  
                                                                                                                         
                                                                                                                         
`,
    "color: #32CD32; background-color: #000; font-family: monospace; padding: 8px 0;"
);
console.log(
    "%c👾 Building with passion, one line at a time. \n https://www.garik.codes \n\n",
    "color: #32CD32; background-color: #000; font-family: monospace; padding: 4px 0;"
);


	inject({ mode: dev ? 'development' : 'production' });

	let { children } = $props();

	let initialRender: boolean = $state(false);
	onMount(() => {
		initialRender = true;
	});

	let path = $derived(
		$page.url.pathname
			.replace(/^\/|\/$/g, '')
			.split('/')
			.map((word) => word.charAt(0).toUpperCase() + word.slice(1))
			.join('/')
	);
</script>

<svelte:head>
	<title>Toska Bear | {path === '' ? 'Home' : path}</title>
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "MusicGroup",
			"name": "Toska Bear",
			"url": "https://toskabear.vercel.app",
			"image": "https://toskabear.vercel.app/JPP.jpeg",
			"description": "Brief description of the artist/band and genre.",
			"genre": "Indie Electronic",
			"sameAs": [
				"https://www.instagram.com/toska_bear",
				"https://www.twitter.com/toskabear",
				"https://www.youtube.com/@TOSKABEAROFFICIAL",
				"https://open.spotify.com/artist/2vrJUCbyPchGh50jrGuzwi",
				"https://music.apple.com/us/artist/toska-bear/1543948390",
				"https://www.facebook.com/jason.c.porter/"
			],
			//   "album": [{
			// 	"@type": "MusicAlbum",
			// 	"name": "Album Title",
			// 	"url": "https://artistwebsite.com/album-title",
			// 	"releaseDate": "2023-09-15",
			// 	"track": [{
			// 	  "@type": "MusicRecording",
			// 	  "name": "Track 1 Title",
			// 	  "url": "https://artistwebsite.com/album-title/track-1",
			// 	  "duration": "PT3M45S"  // Format: PT#M#S
			// 	},
			// 	{
			// 	  "@type": "MusicRecording",
			// 	  "name": "Track 2 Title",
			// 	  "url": "https://artistwebsite.com/album-title/track-2",
			// 	  "duration": "PT4M30S"
			// 	}]
			//   }],
			"foundingLocation": {
				"@type": "Place",
				"name": "Columbus, Ohio"
			},
			"members": [
				{
					"@type": "Person",
					"name": "Jason Porter"
				}
			]
		}
	</script>

	<meta property="og:title" content="Toska Bear | Indie Electronic Bear Musician" />
	<meta property="og:type" content="website" />
	<meta property="og:url" content="https://toskabear.vercel.app" />
	<meta property="og:image" content="https://toskabear.vercel.app/JPP.jpeg" />
	<meta
		property="og:description"
		content="Check out my new album TAKING MY MIND FOR A RIDE on streaming platforms & vinyl!"
	/>
	<meta property="og:site_name" content="Toska Bear | Indie Electronic Bear Musician" />

	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:site" content="@ToskaBear" />
	<meta name="twitter:title" content="Toska Bear" />
	<meta
		name="twitter:description"
		content="Check out my new album TAKING MY MIND FOR A RIDE on streaming platforms & vinyl!"
	/>
	<meta name="twitter:image" content="https://toskabear.vercel.app/JPP.jpeg" />
</svelte:head>

{#if initialRender}
	<div in:fade={{ duration: 1400 }} class="flex h-screen w-full justify-start">
		<Nav />
		<MobileNav />
		<Icons />

		{#key $page.url.pathname}
			<div in:fade={{ duration: 1000 }} class="h-full w-full">
				{@render children()}
			</div>
		{/key}
	</div>
{/if}
