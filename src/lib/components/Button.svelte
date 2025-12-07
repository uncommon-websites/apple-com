<script lang="ts">
    export let variant: 'filled' | 'outline' = 'filled';
    export let href: string = "/";
    export let size: 'small' | 'medium' = 'medium';
</script>

<a 
    {href} 
    class="
        inline-flex items-center justify-center rounded-full transition-all duration-300 font-normal leading-normal
        {size === 'small' ? 'px-4 py-2 text-[14px]' : 'px-5 py-2 text-[17px]'}
        {variant === 'filled' 
            ? 'bg-[#0071e3] text-white hover:bg-[#0077ed]' 
            : 'bg-transparent text-[#0071e3] border border-[#0071e3] hover:bg-[#0071e3] hover:text-white'}
    "
>
    <slot />
</a>
