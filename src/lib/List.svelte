<script lang="ts">
	import { page } from '$app/stores';
</script>

<ul class="space-y-4 p-4">
	<li class="p-2">
		<a href="/" class="hover:opacity-75" aria-label="Home">
			Home<span
				class="transition-opacity {$page.url.pathname === '/' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/about" class="hover:opacity-75" aria-label="About"
            >
			About<span
				class="transition-opacity {$page.url.pathname === '/about' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/vinyl" class="hover:opacity-75" aria-label="Vinyl">
			Vinyl<span
				class="transition-opacity {$page.url.pathname === '/vinyl' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/watch" class="hover:opacity-75" aria-label="Watch">
			Watch<span
				class="transition-opacity {$page.url.pathname === '/watch' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/podcasts" class="hover:opacity-75" aria-label="Podcasts">
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
		<a href="/contact" class="hover:opacity-75" aria-label="Contact"
            >
			Contact<span
				class="transition-opacity {$page.url.pathname === '/contact' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
</ul>
