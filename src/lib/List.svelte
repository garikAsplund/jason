<script lang="ts">
	import { page } from '$app/stores';
</script>

<ul class="space-y-4 p-4">
	<li class="p-2">
		<a href="/" class="hover:opacity-75">
			Home<span
				class="transition-opacity {$page.url.pathname === '/' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/about" class="hover:opacity-75"
            >
			About<span
				class="transition-opacity {$page.url.pathname === '/about' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/vinyl" class="hover:opacity-75">
			Vinyl<span
				class="transition-opacity {$page.url.pathname === '/vinyl' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/watch" class="hover:opacity-75">
			Watch<span
				class="transition-opacity {$page.url.pathname === '/watch' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
	<li class="p-2">
		<a href="/podcasts" class="hover:opacity-75">
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
		<a href="/contact" class="hover:opacity-75"
            >
			Contact<span
				class="transition-opacity {$page.url.pathname === '/contact' ? 'opacity-100' : 'opacity-0'}"
			>
				/</span
			>
		</a>
	</li>
</ul>
