<script lang="ts">
	import { videos } from "$lib/videos";
</script>

<section class="scrollbar-hide max-h-[80vh] overflow-y-auto">
	<div class="mb-48 flex flex-col gap-24 p-4">
	<div class="scroll-down justify-center items-center hidden md:flex"><span></span><span></span></div>	
		{#each videos as video}
			<div class="relative w-full pb-[56.25%]">
				<iframe
					class="absolute inset-0 h-full w-full shadow-md transition-transform duration-300"
					src={`https://www.youtube.com/embed/${video.id}`}
					loading="lazy"
					title="Toska Bear video gallery"
					frameborder="0"
					allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
					allowfullscreen
				>
				</iframe>
			</div>
		{/each}
	</div>
</section>

<style>
	.scroll-down {
		position: relative;
		left: 50%;
		transform: translate(-50%, -50%);
        animation: fade-and-move 4s ease-in-out 1 forwards;
	}

	.scroll-down span {
		display: block;
		width: 20px;
		height: 20px;
		border-bottom: 2px solid #ffffff;
		border-right: 2px solid #ffffff;
		transform: rotate(45deg);
		margin: -10px;
		animation: animate 2s infinite;
	}

	.scroll-down span:nth-child(2) {
		animation-delay: -0.2s;
	}

	.scroll-down span:nth-child(3) {
		animation-delay: -0.4s;
	}

	@keyframes animate {
		0% {
			opacity: 0;
			transform: rotate(45deg) translate(-20px, -20px);
		}
		50% {
			opacity: 0.7;
		}
		100% {
			opacity: 0;
			transform: rotate(45deg) translate(20px, 20px);
		}
	}

     /* The fade-out animation for the scroll indicator */
     @keyframes fade-and-move {
        0%, 50% {
            opacity: 1;
        }
        100% {
            opacity: 0;
        }
    }
</style>
