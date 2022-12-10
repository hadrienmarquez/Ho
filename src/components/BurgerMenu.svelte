<script lang="ts">
    let hidden: string = "hidden";

    function handleClick() {
        hidden = hidden === "hidden" ? "bg-red-400" : "hidden";
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
<div class="fixed top-0 left-0 w-full h-full {hidden} z-50">
    <!-- Popup Menu -->
    <button on:click={handleClick}>Close Me</button>
</div>
