<script>
    let cssClass;
    export { cssClass as class };
    export let url;
    export let after_content;
</script>


<a href={url} {after_content} class="{cssClass} after:content-[attr(after\_content)] font-maragsa z-10 relative after:-z-10 after:absolute after:w-full after:pointer-events-none after:duration-300 after:opacity-0 after:top-0 after:left-0 after:transition-all after:ease-out  hover:after:left-1 hover:after:opacity-100"><slot/></a>
