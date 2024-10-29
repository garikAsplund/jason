<script lang="ts">
	import { page } from '$app/stores';
</script>

<ul class="space-y-4 p-4">
	<li class="p-2">
		<a href="/" class="hover:opacity-75" aria-label="Home">
			<span
				class="transition-opacity {$page.url.pathname === '/' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>Home
		</a>
	</li>
	<li class="p-2">
		<a href="/about" class="hover:opacity-75" aria-label="About"
            >
			<span
				class="transition-opacity {$page.url.pathname === '/about' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>About
		</a>
	</li>
	<li class="p-2">
		<a href="/vinyl" class="hover:opacity-75" aria-label="Vinyl">
			<span
				class="transition-opacity {$page.url.pathname === '/vinyl' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>Vinyl
		</a>
	</li>
	<li class="p-2">
		<a href="/watch" class="hover:opacity-75" aria-label="Watch">
			<span
				class="transition-opacity {$page.url.pathname === '/watch' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>Watch
		</a>
	</li>
	<li class="p-2">
		<a href="/podcasts" class="hover:opacity-75" aria-label="Podcasts">
			<span
				class="transition-opacity {$page.url.pathname === '/podcasts'
					? 'opacity-100'
					: 'opacity-0'}"
			>
				/</span
			>Podcasts
		</a>
	</li>
	<li class="p-2">
		<a href="/contact" class="hover:opacity-75" aria-label="Contact"
            >
			<span
				class="transition-opacity {$page.url.pathname === '/contact' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>Contact
		</a>
	</li>
</ul>
