<script lang="ts">
	import { page } from '$app/state';
</script>

<div class="relative flex h-full w-full flex-col items-center justify-center">
	<div class="flex h-auto w-2/3 flex-col items-center justify-center">
	<enhanced:img src="/static/404.png" class="object-contain w-full h-auto mb-24" alt="Listening to Kanye, I see"/>
	<h1 class="text-3xl text-white/70 mt-16">{page.status}: {page.error?.message}</h1></div>
</div>
