<script lang="ts">
    let hidden: string = "hidden";

    function handleClick() {
        hidden = hidden === "hidden" ? "bg-red-400" : "hidden";
    }
</script>

<div class="bg-red-600 my-auto">
    <button
        on:click={handleClick}
        class="flex md:space-x-2 p-4 md:px-4 md:py-2"
    >
        <p class="hidden md:block my-auto text-sm text-brown-100">Menu</p>
        <div class="my-auto space-y-1">
            <span class="block w-8 h-px bg-brown-100" />
            <span class="block w-8 h-px bg-brown-100" />
            <span class="block w-8 h-px bg-brown-100" />
        </div>
    </button>
</div>

<!-- Popup container class -->
<div class="fixed top-0 left-0 w-full h-full {hidden} z-50">
    <!-- Popup Menu -->
    <button on:click={handleClick}>Close Me</button>
</div>
