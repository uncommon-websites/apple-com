<script lang="ts">
    import Button from './Button.svelte';

    export let title: string = "";
    export let subtitle: string = "";
    export let links: { text: string, href: string, variant?: 'filled' | 'outline' }[] = [];
    // export let theme: 'light' | 'dark' = 'light'; // Controls text color mostly - Unused
    export let backgroundClass: string = "bg-[#f5f5f7]"; // Custom background class
    export let logoSrc: string | null = null;
    export let logoAlt: string = "";
    // export let topContent: boolean = true; // Unused
    export let textColor: string = "text-[#1d1d1f]";
</script>

<div class="{backgroundClass} w-full h-[500px] md:h-[580px] overflow-hidden relative flex flex-col items-center pt-10 md:pt-14 group cursor-pointer">
    <div class="flex flex-col items-center text-center px-4 z-10 relative {textColor}">
        <div class="mb-1 flex items-center justify-center min-h-[32px]">
            <slot name="logo">
                {#if logoSrc}
                    <img src={logoSrc} alt={logoAlt || "Product Logo"} class="h-8 object-contain" />
                {:else if title}
                     <h3 class="text-[32px] md:text-[40px] font-semibold tracking-tight leading-[1.1]">{title}</h3>
                {/if}
            </slot>
        </div>

        {#if subtitle}
            <p class="text-[17px] md:text-[21px] font-normal leading-tight mb-3 max-w-md mt-1">{subtitle}</p>
        {/if}
        
        <div class="flex gap-3 mt-2">
            {#each links as link}
                <Button href={link.href} variant={link.variant || 'filled'} size="small">{link.text}</Button>
            {/each}
        </div>
    </div>

    <div class="absolute bottom-0 w-full flex justify-center items-end h-full transition-transform duration-500 group-hover:scale-[1.02]">
        <slot name="image"></slot>
    </div>
</div>
