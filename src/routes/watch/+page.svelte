<script lang="ts">
	import Videos from '$lib/Videos.svelte';
	import TESTVIDS from '$lib/TESTVIDS.svelte';
</script>

<svelte:head>
	<meta name="description" content="Watch Toska Bear's videos on YouTube." />
</svelte:head>

<div class="relative flex h-screen w-full flex-col bg-black">

	<div class="mt-16 flex-1 overflow-y-auto p-5">
		<div class="relative mx-auto sm:flex w-full justify-center items-center hidden">
			<Videos />
			<!-- <TESTVIDS /> -->
		</div>
		<div class="relative mx-auto w-full justify-center items-center sm:hidden flex">
			<!-- <Videos /> -->
			<TESTVIDS />
		</div>
	</div>
</div>