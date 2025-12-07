<script lang="ts">
    import Button from './Button.svelte';

    export let title: string;
    export let subtitle: string;
    export let links: { text: string, href: string, variant?: 'filled' | 'outline' }[] = [];
    export let theme: 'light' | 'dark' = 'light';
    export let imageSrc: string | null = null;
    export let imageAlt: string = "";
    export let logoSrc: string | null = null;
    // export let customContent: any = null; // Unused
</script>

<section class="w-full relative overflow-hidden pt-12 pb-12 {theme === 'dark' ? 'bg-black text-white' : 'bg-[#f5f5f7] text-[#1d1d1f]'}">
    <div class="flex flex-col items-center text-center px-4 z-10 relative">
        {#if logoSrc}
            <img src={logoSrc} alt={title || "Product Logo"} class="h-8 mb-3" />
        {:else}
            <h2 class="text-[32px] md:text-[56px] font-semibold tracking-tight leading-[1.1] mb-1">{title}</h2>
        {/if}
        
        <p class="text-[19px] md:text-[28px] font-normal leading-tight mb-3 max-w-2xl">{subtitle}</p>
        
        <div class="flex gap-4 mt-1">
            {#each links as link}
                <Button href={link.href} variant={link.variant || 'filled'}>{link.text}</Button>
            {/each}
        </div>
    </div>

    <div class="mt-10 md:mt-14 w-full flex justify-center">
        {#if imageSrc}
            <img src={imageSrc} alt={imageAlt} class="h-[300px] md:h-[500px] object-contain" />
        {:else}
            <slot name="image"></slot>
        {/if}
    </div>
</section>
