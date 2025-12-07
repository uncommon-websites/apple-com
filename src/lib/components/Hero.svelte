<script lang="ts">
  export let title: string = "";
  export let subtitle: string = "";
  export let buttons: { label: string; href: string; type?: 'primary' | 'secondary' }[] = [];
  export let image: string = "";
  export let theme: 'light' | 'dark' = 'light';
  export let customContent: boolean = false;
  export let logo: boolean = false; 
  export let logoContent: string = ""; 
  export let className: string = "";
</script>

<section class="w-full relative overflow-hidden pt-[55px] pb-[50px] md:pt-[60px] md:pb-[60px] flex flex-col items-center text-center {theme === 'dark' ? 'bg-black text-white' : 'bg-white text-[#1d1d1f]'} {className}">
  
  <div class="z-10 flex flex-col items-center w-full max-w-[800px] px-4">
    {#if logo}
      <div class="mb-4">
        <slot name="logoContent">
            {@html logoContent}
        </slot>
      </div>
    {:else if title}
      <h2 class="text-[32px] md:text-[56px] leading-[1.07] font-semibold tracking-tight mb-1.5">{title}</h2>
    {/if}

    {#if subtitle}
      <p class="text-[19px] md:text-[28px] leading-[1.1] font-normal tracking-tight mb-3">{subtitle}</p>
    {/if}

    {#if buttons.length > 0}
      <div class="flex gap-4 mt-3">
        {#each buttons as btn}
          <a href={btn.href} class="rounded-full px-5 py-2 text-[17px] font-normal transition-all duration-300 {btn.type === 'secondary' ? 'text-[#0066cc] hover:underline' : 'bg-[#0071e3] text-white hover:bg-[#0077ed]'}">
            {btn.label}
          </a>
        {/each}
      </div>
    {/if}
  </div>

  {#if customContent}
    <slot />
  {:else if image}
    <div class="mt-10 md:mt-14 w-full flex justify-center">
      <img src={image} alt={title} class="h-[300px] md:h-[500px] object-contain" />
    </div>
  {/if}
</section>
