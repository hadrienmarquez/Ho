<script lang="ts">
    import { fade, scale } from "svelte/transition";
    import DisplaceLink from "./DisplaceLink.svelte";
    import StyledButton from "./StyledButton.svelte";
    let visible = false;

    const links = [
        {
            url: "/a-propos",
            text: "À propos",
        },
        {
            url: "/journal-de-bord",
            text: "Journal de bord",
        },
        {
            url: "/contact",
            text: "Contact",
        },
    ];

    function handleClick() {
        visible = !visible;
    }
</script>

<StyledButton showText={false} on:click={handleClick}>
    <span slot="text">Menu</span>
    <div class="my-auto space-y-1 z-10 flex flex-col justify-center">
        <span
            class="block w-8 h-px bg-brown-100 duration-300 group-hover:bg-brown-800"
        />
        <span
            class="block w-8 h-px bg-brown-100 duration-300 group-hover:bg-brown-800"
        />
        <span
            class="block w-8 h-px bg-brown-100 duration-300 group-hover:bg-brown-800"
        />
    </div>
</StyledButton>

<!-- Popup container class -->
{#if visible}
    <div
        in:fade={{ duration: 500 }}
        out:fade={{ duration: 500, delay: 300 }}
        class="flex items-start justify-end fixed top-0 left-0 w-full h-full bg-yellow-300 bg-opacity-80 z-50 sm:justify-center sm:items-center"
    >
        <div
            in:scale={{ duration: 500, delay: 200 }}
            out:scale={{ duration: 500 }}
            class=" flex flex-col items-start justify-around bg-green-700 rounded-3xl w-fit m-2 px-10 h-[28rem] sm:items-center sm:rounded-full sm:p-0 sm:m-0 sm:w-[400px] sm:h-[400px] md:w-[500px] md:h-[500px]"
        >
            <div
                class="flex flex-col justify-between items-start space-y-4 text-4xl h-fit sm:mt-[5rem] sm:items-center sm:space-y-8 sm:mb-7 sm:text-5xl  md:text-6xl md:mt-[6rem] md:space-y-10"
            >
                {#each links as link}
                    <DisplaceLink
                        class="text-brown-100 after:text-red-400"
                        after_content={link.text}
                        url={link.url}>{link.text}</DisplaceLink
                    >
                    <span class="w-full sm:hidden border-b border-red-300" />
                {/each}
            </div>
            <button
                on:click={handleClick}
                class="relative text-brown-100 z-10 font-maragsa  border-red-400 border rounded-full text-2xl text-center self-end h-10 w-10 sm:h-8 sm:w-8 sm:self-center  sm:border-0  md:h-12 md:w-12 md:text-3xl md:font-bold after:rounded-full after:absolute after:-z-10 after:scale-0 after:top-0 after:-left-0 after:w-full after:h-full after:bg-red-400 hover:after:scale-150 after:transition-transform"
                >X</button
            >
        </div>
        <!-- Popup Menu -->
    </div>
{/if}
