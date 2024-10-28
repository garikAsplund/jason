<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import '../app.css';
	import { page } from '$app/stores';
	import Icons from '$lib/Icons.svelte';
	import Nav from '$lib/Nav.svelte';

	let { children } = $props();

	let initialRender: boolean = $state(false);
	onMount(() => {
		initialRender = true;
	});
</script>

{#if initialRender}
	<div in:fade={{ duration: 1400 }} class="flex h-screen w-full justify-start">
		<Nav />		

		{#key $page.url.pathname}
		<Icons />
			<div in:fade={{ duration: 1000 }} class="w-full h-full">
				{@render children()}
			</div>
		{/key}
	</div>
{/if}
