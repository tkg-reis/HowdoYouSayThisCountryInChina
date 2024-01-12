<!-- +++++ js +++++ -->
<script>
    export let gistURL = "";

    import { onMount } from "svelte";

    let frame;

    onMount(() => {
        frame.srcdoc = `<script src='${gistURL}.js'><${""}/script>`;
    })
</script>
<!-- +++++ end +++++ -->
<!-- end -->
<!-- +++++ html +++++ -->
<iframe src="about:blank" bind:this={frame} title="Gist"></iframe>
<!-- +++++ end +++++ -->
<!-- +++++ css +++++ -->
<style>
    iframe {
        width: 100%;
        height: 100%;
        border: none;
    }
</style>
<!-- +++++ end +++++ -->