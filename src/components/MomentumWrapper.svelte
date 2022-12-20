<script lang="ts">
    import { onMount } from "svelte";
    let momentum_wrapper: HTMLDivElement;

    function lerp(x0: number, x1: number, t: number): number {
        return (1 - t) * x0 + x1 * t;
    }

    let cur_x = 0;
    let cur_y = 0;
    let scroll_x = 0;
    let scroll_y = 0;

    // Dom related stuff is done after component has mounted
    onMount(() => {
        const body = document.body;

        body.style.height = momentum_wrapper.clientHeight + "px";

        let frame = requestAnimationFrame(loop);

        function loop(t: DOMHighResTimeStamp) {
            scroll_x = window.scrollX;
            scroll_y = window.scrollY;

            cur_x = lerp(cur_x, scroll_x, 0.07);
            cur_y = lerp(cur_y, scroll_y, 0.07);

            cur_x = Math.floor(cur_x * 100) / 100;
            cur_y = Math.floor(cur_y * 100) / 100;

            momentum_wrapper.style.transform = `translate3d(-${cur_x}px, -${cur_y}px, 0px`;

            frame = requestAnimationFrame(loop);
        }

        const resizeObserver = new ResizeObserver((entries) => {
            const entry = entries.at(0);
            if (entry === undefined) {
                return;
            } else {

                body.style.height = entry.contentRect.height + "px";
               
            }
        });

        resizeObserver.observe(momentum_wrapper);

        return () => {
            cancelAnimationFrame(frame);
            resizeObserver.unobserve(momentum_wrapper);
        };
    });
</script>

<div bind:this={momentum_wrapper} class="fixed w-screen top-0 left-0">
    <slot />
</div>
