<svelte:head>
    <meta name="description" content="Purchase Toska Bear's LPs." />
</svelte:head>

<div class="relative h-screen w-full bg-black">
    <enhanced:img src="/static/tunnel.jpg" alt="Toska tunnel" class="h-full w-full object-cover" />
    <div class="absolute inset-0 z-0 bg-black/60"></div>
    <!-- Container for the album images -->
    <div class="absolute inset-0 flex items-center justify-center z-10">
        <div class="flex flex-col items-center space-y-8 md:space-y-16 px-4 w-full">
            <div class="w-[80%] md:w-[30%]">
               <a 
                    href="https://toskabear.myshopify.com/products/taking-my-mind-for-a-ride-vinyl-record-pre-order"
                    target="_blank"
                    aria-label="Purchase Take My Mind for a Ride on vinyl"
                    rel="noopener noreferrer"
                    class="relative block aspect-square"
                >
                    <enhanced:img 
                        src="/static/TMMFAR.jpeg" 
						alt="Takes My Mind for a Ride on vinyl"
                        class="w-full h-full object-contain"
                    />
                    <div class="absolute inset-0 bg-white opacity-0 hover:opacity-10 transition-opacity duration-300"></div>
                </a>
            </div>
            <div class="w-[80%] md:w-[30%]">
                <a
                    href="https://toskabear.myshopify.com/products/year-of-the-beard-vinyl-record"
                    target="_blank"
                    aria-label="Purchase Year of the Beard on vinyl"
                    rel="noopener noreferrer"
                    class="relative block aspect-square"
                >
                    <enhanced:img 
                        src="/static/year-of-the-beard.jpg" 
						alt="Year of the Beard on vinyl"
                        class="w-full h-full object-contain"
                    />
                    <div class="absolute inset-0 bg-white opacity-0 hover:opacity-10 transition-opacity duration-300"></div>
                </a>
            </div>
        </div>
    </div>
</div>