<script lang="ts">
	import { videos } from '$lib/videos';
	function labnolIframe(div) {
		const iframe = document.createElement('iframe');
		iframe.setAttribute(
			'src',
			'https://www.youtube.com/embed/' + div.dataset.id + '?autoplay=1&rel=0'
		);
		iframe.setAttribute('frameborder', '0');
		iframe.setAttribute('allowfullscreen', '1');
		iframe.setAttribute('class', "absolute inset-0 h-full w-full");
		iframe.setAttribute(
			'allow',
			'accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture'
		);
		div.parentNode.replaceChild(iframe, div);
	}
	function initYouTubeVideos() {
		const playerElements = document.querySelectorAll('.youtube-player');
		playerElements.forEach((player) => {
			const videoId = player.dataset.id;
			const div = document.createElement('div');
			div.setAttribute('data-id', videoId);
			// Create and append thumbnail
			const thumbNode = document.createElement('img');
			thumbNode.src = `https://i.ytimg.com/vi/${videoId}/hqdefault.jpg`;
			thumbNode.classList.add('thumbnail');
			div.appendChild(thumbNode);
			// Add play button overlay
			const playButton = document.createElement('div');
			playButton.setAttribute('class', 'play');
            playButton.innerHTML = `
            <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" style="width: 68px; height: 48px; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -20%);">
                <path 
                    fill="none" 
                    stroke="white" 
                    stroke-width="1" 
                    stroke-linejoin="round"
                    d="M20.5949 4.45999C21.5421 4.71353 22.2865 5.45785 22.54 6.40501C22.9982 8.12001 23 11.7004 23 11.7004C23 11.7004 23 15.2807 22.54 16.9957C22.2865 17.9429 21.5421 18.6872 20.5949 18.9407C18.88 19.4007 12 19.4007 12 19.4007C12 19.4007 5.12001 19.4007 3.405 18.9407C2.45785 18.6872 1.71353 17.9429 1.45999 16.9957C1 15.2807 1 11.7004 1 11.7004C1 11.7004 1 8.12001 1.45999 6.40501C1.71353 5.45785 2.45785 4.71353 3.405 4.45999C5.12001 4 12 4 12 4C12 4 18.88 4 20.5949 4.45999ZM15.5134 11.7007L9.79788 15.0003V8.40101L15.5134 11.7007Z"
                />
            </svg>
        `;
			div.appendChild(playButton);
			// Replace thumbnail with iframe on click
			div.onclick = function () {
				labnolIframe(this);
			};
			player.appendChild(div);
		});
	}
	import { afterUpdate } from 'svelte';
	afterUpdate(() => {
		initYouTubeVideos();
        console.log(document.querySelector('.play'))
	});
</script>

<section class="scrollbar-hide max-h-[85vh] w-full overflow-y-auto">
	<div class="mb-48 flex flex-col">
		<div class="scroll-down hidden items-center justify-center md:flex">
			<span></span><span></span>
		</div>
		{#each videos as video}
			<div class="youtube-player" data-id={video.id}>
                
            </div>
		{/each}
	</div>
</section>

<style>
	.youtube-player {
		position: relative;
		padding-bottom: 56.25%;
		height: 0;
		overflow: hidden;
		max-width: 100%;
		background: #000;
		margin: 5px;
	}
	.youtube-player iframe {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		z-index: 100;
		background: transparent;
	}
	.youtube-player img.thumbnail {
		object-fit: cover;
		display: block;
		width: 100%;
		height: 100%;
		position: absolute;
		top: 0;
		left: 0;
		border: none;
		cursor: pointer;
		transition: filter 0.4s;
	}
	.youtube-player img.thumbnail:hover {
		filter: brightness(75%);
	}
	.youtube-player .play {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;  
        align-items: center;  
        justify-content: center;  
        cursor: pointer;
        z-index: 200;
    }

    .youtube-player .play::before {
        content: '';
        width: 68px;
        height: 48px;
        background-repeat: no-repeat;
        background-position: center;
        background-size: contain;
        position: absolute;
    }

	.youtube-player .play:hover::before {
		opacity: 1;
	}
</style>