<script lang="ts">
	import { Drawer, SidebarGroup, SidebarItem, Sidebar, SidebarWrapper } from 'flowbite-svelte';
	import List from './List.svelte';
	import { page } from '$app/stores';
	let hidden2: boolean = $state(true);
	let transitionParams = {
		x: 320,
		duration: 200
	};
</script>

<div
	class="fixed -right-5 bottom-36 z-20 flex -rotate-90 items-center text-center md:hidden {hidden2
		? ''
		: 'hidden'}"
>
	<button
		onclick={() => (hidden2 = false)}
		class="flex items-center justify-center bg-black/70 text-orange-500/70"
	>
		<p class="py-2 px-4 text-xl">MENU</p>
		<svg
			xmlns="http://www.w3.org/2000/svg"
			width="24"
			height="24"
			viewBox="0 0 24 24"
			fill="none"
			stroke="rgb(255 90 31 / 0.7)"
			stroke-width="2"
			stroke-linecap="round"
			stroke-linejoin="round"
			class="lucide lucide-chevrons-left rotate-90"
		>
			<path d="m11 17-5-5 5-5" />
			<path d="m18 17-5-5 5-5" />
		</svg>
	</button>
</div>

<Drawer
	placement="right"
	class="flex w-full flex-col items-center justify-center bg-transparent text-white"
	transitionType="fly"
	{transitionParams}
	bind:hidden={hidden2}
	id="sidebar2"
>
	<Sidebar>
		<nav
			class="h-full flex-col items-center justify-center font-mono text-4xl text-white text-opacity-85 md:flex md:w-1/4"
		>
			<ul class="space-y-4 p-4">
				<li class="p-2">
					<a href="/" class="hover:opacity-75" onclick={() => (hidden2 = true)}>
						Home<span
							class="transition-opacity {$page.url.pathname === '/' ? 'opacity-100' : 'opacity-0'}"
						>
							/</span
						>
					</a>
				</li>
				<li class="p-2">
					<a href="/about" class="hover:opacity-75" onclick={() => (hidden2 = true)}>
						About<span
							class="transition-opacity {$page.url.pathname === '/about'
								? 'opacity-100'
								: 'opacity-0'}"
						>
							/</span
						>
					</a>
				</li>
				<li class="p-2">
					<a href="/vinyl" class="hover:opacity-75" onclick={() => (hidden2 = true)}>
						Vinyl<span
							class="transition-opacity {$page.url.pathname === '/vinyl'
								? 'opacity-100'
								: 'opacity-0'}"
						>
							/</span
						>
					</a>
				</li>
				<li class="p-2">
					<a href="/watch" class="hover:opacity-75" onclick={() => (hidden2 = true)}>
						Watch<span
							class="transition-opacity {$page.url.pathname === '/watch'
								? 'opacity-100'
								: 'opacity-0'}"
						>
							/</span
						>
					</a>
				</li>
				<li class="p-2">
					<a href="/podcasts" class="hover:opacity-75" onclick={() => (hidden2 = true)}>
						Podcasts<span
							class="transition-opacity {$page.url.pathname === '/podcasts'
								? 'opacity-100'
								: 'opacity-0'}"
						>
							/</span
						>
					</a>
				</li>
				<li class="p-2">
					<a href="/contact" class="hover:opacity-75" onclick={() => (hidden2 = true)}>
						Contact<span
							class="transition-opacity {$page.url.pathname === '/contact'
								? 'opacity-100'
								: 'opacity-0'}"
						>
							/</span
						>
					</a>
				</li>
			</ul>
		</nav>
		<div class="fixed -right-5 bottom-36 -rotate-90">
			<button
				onclick={() => (hidden2 = true)}
				class="flex items-center justify-center bg-transparent text-orange-500/70"
			>
				<p class="p-2 text-xl">CLOSE</p>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					width="24"
					height="24"
					viewBox="0 0 24 24"
					fill="none"
					stroke="rgb(255 90 31 / 0.7)"
					stroke-width="2"
					stroke-linecap="round"
					stroke-linejoin="round"
					class="lucide lucide-chevrons-left -rotate-90"
				>
					<path d="m11 17-5-5 5-5" />
					<path d="m18 17-5-5 5-5" />
				</svg>
			</button>
		</div>
	</Sidebar>
</Drawer>
