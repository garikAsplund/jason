<script lang="ts">
	import List from './List.svelte';
	import Watermark from './Watermark.svelte';
</script>
<nav
	class="hidden h-full flex-col items-center justify-between pl-8 font-mono text-4xl text-white text-opacity-85 md:flex md:w-1/4"
>
	<div class="flex flex-col items-center justify-center h-full">
		<List />
	</div>
	<div class="mb-8">
		<Watermark />
	</div>
</nav>