<script lang="ts">
    import { fade } from 'svelte/transition';
    let visible = false;

    function handleClick() {
        visible = !visible;
        console.log(visible)
    }
</script>

<div class="group my-auto border border-brown-100 bg-red-700 relative after:w-full after:h-full after:bg-brown-400 after:-z-10 after:absolute after:top-1 after:left-1 after:transition-all after:ease-out after:duration-300  hover:after:left-0 hover:after:top-0">
    <button
        on:click={handleClick}
        class="flex md:space-x-2 p-4 md:px-4 md:py-2 z-10 after:z-0 after:absolute after:w-full after:h-full after:bg-brown-300 after:top-0 after:left-0 after:scale-y-0 after:transition-transform after:duration-300 after:ease-out after:origin-bottom-left group-hover:after:scale-100 after:delay-75"
    >
        <p class="hidden md:block my-auto text-sm font-bold text-brown-100 z-10 duration-300 group-hover:text-brown-800">Menu</p>
        <div class="my-auto space-y-1 z-10">
            <span class="block w-8 h-px bg-brown-100 duration-300 group-hover:bg-brown-800" />
            <span class="block w-8 h-px bg-brown-100 duration-300 group-hover:bg-brown-800" />
            <span class="block w-8 h-px bg-brown-100 duration-300 group-hover:bg-brown-800" />
        </div>
    </button>
</div>




<!-- Popup container class -->
{#if visible}
<div in:fade="{{duration: 150}}" out:fade="{{duration: 200}}" class="flex items-start justify-end fixed top-0 left-0 w-full h-full bg-yellow-300 bg-opacity-80 z-50" >
    <div class="bg-green-700 rounded-full w-[250px] h-[250px] m-2 md:w-[500px] md:h-[500px]">
        <div class="flex flex-col items-center justify-around h-full">
            <div class="flex flex-col justify-between items-center space-y-2 text-3xl mt-10 md:text-6xl md:space-y-10 md:mb-7 h-fit">
                <a href="/a-propos" class="text-brown-100 font-maragsa z-10  
                relative  after:content-['À\00a0propos']  after:-z-10
                 after:text-red-400
                 after:absolute after:pointer-events-none after:duration-300 after:opacity-0 after:top-0 after:left-0 after:transition-all after:ease-in-out  hover:after:opacity-100 hover:after:left-1">À&nbsp;propos</a>
                <a href="/journal-de-bord" class="text-brown-100 font-maragsa z-10  
                relative after:content-['Journal\0000a0de\0000a0bord']  after:-z-10
                 after:text-red-400
                 after:absolute after:pointer-events-none after:duration-300 after:opacity-0 after:top-0 after:left-0 after:transition-all after:ease-in-out  hover:after:opacity-100 hover:after:left-1">Journal&nbsp;de&nbsp;bord</a>
                <a href="/contact" class="text-brown-100 font-maragsa z-10  
                relative  after:content-['Contact']  after:-z-10
                 after:text-red-400
                 after:absolute after:pointer-events-none after:duration-300 after:opacity-0 after:top-0 after:left-0 after:transition-all after:ease-in-out  hover:after:opacity-100 hover:after:left-1">Contact</a>
            </div>
            <button on:click={handleClick} class="relative text-xl text-center h-8 w-8 md:h-12 md:w-12 md:text-3xl font-bold text-brown-100 z-10 font-maragsa after:rounded-full after:absolute after:-z-10 after:scale-0 after:top-0 after:-left-0 after:w-full after:h-full after:bg-red-400 hover:after:scale-150 after:transition-transform">X</button>
        </div>
    </div>
    <!-- Popup Menu -->

</div>
{/if}