<script lang="ts">
  import { onMount } from 'svelte';
  import Button from './Button.svelte';
  
  export let items: { 
    image?: string,
    gradient?: string, 
    logo?: string, 
    title?: string, 
    subtitle?: string, 
    action?: string, 
    genre?: string,
    type?: string,
    textColor?: string
  }[] = [];
  export let autoPlayInterval = 5000;

  let currentIndex = 0;
  let interval: any;
  let isPaused = false;

  function next() {
    currentIndex = (currentIndex + 1) % items.length;
  }

  function prev() {
    currentIndex = (currentIndex - 1 + items.length) % items.length;
  }

  function goTo(index: number) {
    currentIndex = index;
  }

  function togglePause() {
    isPaused = !isPaused;
    if (isPaused) {
      clearInterval(interval);
    } else {
      startAutoPlay();
    }
  }

  function startAutoPlay() {
    clearInterval(interval);
    interval = setInterval(() => {
      if (!isPaused) next();
    }, autoPlayInterval);
  }

  onMount(() => {
    // Only start if we have items
    if (items.length > 0) {
      startAutoPlay();
    }
    return () => clearInterval(interval);
  });
</script>

<div class="relative w-full overflow-hidden group bg-black pb-4">
  <!-- Slides Container -->
  <div class="relative w-full h-[500px] md:h-[600px]">
      {#each items as item, i}
        <div class="absolute inset-0 transition-opacity duration-700 ease-in-out {i === currentIndex ? 'opacity-100 z-10' : 'opacity-0 z-0'}">
            <div class="relative w-full h-full flex items-center justify-center bg-black overflow-hidden cursor-pointer">
                <!-- Background Image or Gradient -->
                <div class="absolute inset-0 transition-transform duration-700 hover:scale-105">
                    {#if item.image}
                        <img src={item.image} class="w-full h-full object-cover opacity-80" alt={item.title || "Carousel Item"} />
                    {:else if item.gradient}
                        <div class="w-full h-full {item.gradient}"></div>
                    {/if}
                    <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent to-transparent"></div>
                </div>
                
                <!-- Content -->
                <div class="absolute bottom-16 md:bottom-20 flex flex-col items-center md:items-start w-full max-w-[980px] px-6 md:px-0 mx-auto text-center md:text-left {item.textColor || 'text-white'}">
                    {#if item.type || item.genre}
                        <div class="flex items-center gap-3 mb-4 justify-center md:justify-start">
                            {#if item.type}<span class="bg-white text-black text-[10px] font-bold px-1.5 py-0.5 rounded-[3px]">{item.type}</span>{/if}
                            {#if item.genre}<span class="uppercase tracking-widest text-xs font-semibold text-gray-300">{item.genre}</span>{/if}
                        </div>
                    {/if}
                    
                    {#if item.logo}
                        <img src={item.logo} alt={item.title} class="h-24 md:h-32 object-contain mb-4 drop-shadow-2xl" />
                    {:else if item.title}
                        <h2 class="text-5xl md:text-7xl font-black uppercase drop-shadow-2xl font-sans italic leading-[0.9] mb-4">
                            {@html item.title}
                        </h2>
                    {/if}
                    
                    <div class="flex flex-col md:flex-row items-center gap-4 mt-2">
                        {#if item.subtitle}<p class="text-xl md:text-2xl font-medium drop-shadow-md">{item.subtitle}</p>{/if}
                        {#if item.action}
                            <Button href="/" variant="filled" size="medium"><span class="flex items-center gap-2">{item.action} <svg class="w-3 h-3 fill-current" viewBox="0 0 16 16"><path d="M8 13.5c3.038 0 5.5-2.462 5.5-5.5s-2.462-5.5-5.5-5.5-5.5 2.462-5.5 5.5 2.462 5.5 5.5 5.5zM8 15c-3.866 0-7-3.134-7-7s3.134-7 7-7 7 3.134 7 7-3.134 7-7 7zM6.5 5.5l4.5 2.5-4.5 2.5v-5z"></path></svg></span></Button>
                        {/if}
                    </div>
                </div>
            </div>
        </div>
      {/each}
  </div>

  <!-- Pagination Dots -->
  <div class="absolute bottom-6 flex gap-3 justify-center w-full z-20">
       {#each items as _, i}
         <button 
            on:click={() => goTo(i)}
            class="w-2 h-2 rounded-full transition-colors {i === currentIndex ? 'bg-white' : 'bg-white/40 hover:bg-white'}"
            aria-label="Go to slide {i + 1}"
         ></button>
       {/each}
       
       <!-- Pause Button -->
       <button on:click={togglePause} class="w-4 h-4 rounded-full border border-white/40 flex items-center justify-center text-white/60 hover:text-white hover:border-white transition-colors ml-2">
           {#if isPaused}
             <svg class="w-2 h-2 fill-current" viewBox="0 0 16 16"><path d="M3 3l10 5-10 5V3z"></path></svg>
           {:else}
             <svg class="w-2 h-2 fill-current" viewBox="0 0 16 16"><path d="M4.5 3h2v10h-2v-10zM9.5 3h2v10h-2v-10z"></path></svg>
           {/if}
       </button>
  </div>
  
  <!-- Arrow Controls (Visible on Hover) -->
  <button on:click={prev} aria-label="Previous slide" class="absolute left-4 top-1/2 -translate-y-1/2 bg-black/30 text-white p-4 rounded-full opacity-0 group-hover:opacity-100 transition-opacity hover:bg-black/50 z-20 hidden md:block">
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-6 h-6">
      <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
    </svg>
  </button>
  
  <button on:click={next} aria-label="Next slide" class="absolute right-4 top-1/2 -translate-y-1/2 bg-black/30 text-white p-4 rounded-full opacity-0 group-hover:opacity-100 transition-opacity hover:bg-black/50 z-20 hidden md:block">
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-6 h-6">
      <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
    </svg>
  </button>
</div>
