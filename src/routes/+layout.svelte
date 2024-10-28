<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import '../app.css';
	import { page } from '$app/stores';
	import Icons from '$lib/Icons.svelte';
	import Nav from '$lib/Nav.svelte';
	import MobileNav from '$lib/MobileNav.svelte';

	let { children } = $props();

	let initialRender: boolean = $state(false);
	onMount(() => {
		initialRender = true;
	});

	let path = $derived($page.url.pathname
		.replace(/^\/|\/$/g, '')
		.split('/')
		.map((word) => word.charAt(0).toUpperCase() + word.slice(1))
		.join('/'));
</script>

<svelte:head>
	<title>Toska Bear | {path === '' ? 'Home' : path}</title>
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
