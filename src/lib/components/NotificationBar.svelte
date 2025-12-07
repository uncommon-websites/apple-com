<script lang="ts">
    export let text: string;
    export let linkText: string;
    export let href: string = "/";
</script>

<div class="bg-[#1d1d1f] text-white text-[12px] py-3 text-center px-4">
    <p class="inline-block leading-normal">
        {text}
        <a {href} class="text-[#2997ff] hover:underline whitespace-nowrap ml-1">{linkText} <span class="text-[10px] align-middle">›</span></a>
    </p>
</div>
