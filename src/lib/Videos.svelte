<script lang="ts">
	const videos: { id: string }[] = [
		{ id: 'bgV3pmqWFs8?si=PZ0CBCE3OGDfcpu5' },
		{ id: '1gDY_psfqX0?si=42A__46qGl_y7Zj7' },
		{ id: 'bkGOggv9Jsg?si=c_f4xDoXuqs2Jf_5' },
		{ id: 'j3etqMHmN-4?si=sxFSvBz0qGZjJPtC' },
		{ id: '-9QO94WBVSY?si=AY8c0U1UtsX0olut' },
		{ id: '2ZKFEX4Ccgg?si=sOwKNHzXGI_oTiAd' },
		{ id: 'itYg7TieT5Y?si=Iqbwd2ZGuMqOjaOf' },
		{ id: '0IIcCCqgG2c?si=Yp0XK1f2Lwrm9qL4' },
		{ id: 'HcAIVxJLQLU?si=6oY6zRnU2f4k9ydP' },
		{ id: 'wYV96HFx8xA?si=Yb6W9wH80eR4aW_S' },
		{ id: 'zhk_ZZkEFM4?si=TfbxMXISWOOsIObE' },
		{ id: 'xAXwtSHC4uA?si=iTtKTsVsRfTR5eR9' },
		{ id: '71TMCneFOTI?si=fmEcbYMuNOuOxq2t' },
		{ id: '4U172YJO5Kw?si=TaiC8p905gvCfYCr' },
		{ id: 'hPDVrpe04x0?si=bee9KexFcAhvsCmg' }
	];
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
