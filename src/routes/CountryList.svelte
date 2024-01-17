<!-- +++++ js +++++ -->
<script>
    import Header from "../components/Header.svelte";
    import Footer from "../components/Footer.svelte";
    import Gist from "../lib/Gist.svelte";
    

</script>
<!-- +++++ end +++++ -->
<!-- end -->
<!-- +++++ html +++++ -->
<div class="flex_center">
    <Header/>
</div>
<main>
    <h1>coutry list</h1>
    <Gist gistURL="https://gist.github.com/arthur87/5a55aecbe9eb445502aac3193f8e6e80" />
    <!-- {#each  as }
        {#if }
            該当する文字ならcoloringRedコンポーネントで囲む
        {/if}
    {/each} -->
</main>
<Footer/>
<!-- +++++ end +++++ -->
<!-- +++++ css +++++ -->
<style>
    .flex_center{
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
<!-- +++++ end +++++ -->