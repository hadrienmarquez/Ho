<script lang="ts">
    let cssClass = "";
    export let showText = true;
    export { cssClass as class };

    let innerWidth: number = 0;
</script>

<svelte:window bind:innerWidth />
<div
    class=" {cssClass} group my-auto border border-brown-100 bg-red-700 relative after:w-full after:h-full after:bg-brown-400 after:-z-10 after:absolute after:top-1 after:left-1 after:transition-all after:ease-out after:duration-300  hover:after:left-0 hover:after:top-0"
>
    <button
        on:click
        class="flex z-10 p-4 md:space-x-2 md:px-4 md:py-2 after:z-0 after:absolute after:w-full after:h-full after:bg-brown-300 after:top-0 after:left-0 after:scale-y-0 after:transition-transform after:duration-300 after:ease-out after:origin-bottom-left group-hover:after:scale-100 after:delay-75"
    >
        {#if showText || innerWidth >= 768}
            <p
                class="font-sans my-auto text-sm font-bold text-brown-100 z-10 duration-300 group-hover:text-brown-800"
            >
                <slot name="text" />
            </p>
        {/if}
        <slot />
    </button>
</div>
