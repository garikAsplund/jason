<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import '../app.css';
	import { page } from '$app/stores';
	import Icons from '$lib/Icons.svelte';

	let { children } = $props();

	let initialRender: boolean = $state(false);
	onMount(() => {
		initialRender = true;
	});
</script>

{#if initialRender}
	<div in:fade={{ duration: 1400 }} class="flex h-screen w-full justify-start">
		<nav
			class="hidden h-full flex-col items-center justify-center font-mono text-4xl text-white text-opacity-85 md:flex md:w-1/4"
		>
			<ul class="p-4 space-y-4">
				<li class="p-2">
					<a href="/" class="hover:opacity-75">Home</a>
				</li>
				<li class="p-2">
					<a href="/about" class="hover:opacity-75">About</a>
				</li>
				<li class="p-2">
					<a href="/vinyl" class="hover:opacity-75">Vinyl</a>
				</li>
				<li class="p-2">
					<a href="/watch" class="hover:opacity-75">Watch</a>
				</li>
				<li class="p-2">
					<a href="/podcasts" class="hover:opacity-75">Podcasts</a>
				</li>
				<li class="p-2">
					<a href="/contact" class="hover:opacity-75">Contact</a>
				</li>
			</ul>
		</nav>			

		{#key $page.url.pathname}
		<Icons />
			<div in:fade={{ duration: 1000 }} class="w-full h-full">
				{@render children()}
			</div>
		{/key}
	</div>
{/if}
