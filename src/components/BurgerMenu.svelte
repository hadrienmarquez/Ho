<script lang="ts">
    let hidden: string = "bg-yellow-400";

    function handleClick() {
        hidden = hidden === "hidden" ? "bg-yellow-400" : "hidden";
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
<div class="flex items-start justify-end fixed top-0 left-0 w-full h-full {hidden} z-50 bg-opacity-80" >
    <div class="bg-green-700 rounded-full w-[250px] h-[250px] m-2 md:w-[500px] md:h-[500px]">
        <div class="flex flex-col items-center justify-around h-full overflow-hidden">
            <div class="flex flex-col justify-between items-center space-y-2 text-3xl mt-10 md:text-6xl md:space-y-10 md:mb-7 h-fit">
                <a href="/a-propos" class="text-brown-100 font-maragsa">À propos</a>
                <a href="/journal-de-bord" class="text-brown-100 font-maragsa">Journal de bord</a>
                <a href="/contact" class="text-brown-100 font-maragsa">Contact</a>
            </div>
            <button on:click={handleClick} class=" text-brown-100 text-xl  font-maragsa md:text-3xl font-bold">X</button>
        </div>
    </div>
    <!-- Popup Menu -->

</div>
