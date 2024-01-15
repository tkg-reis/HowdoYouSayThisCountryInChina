<!-- +++++ js +++++ -->
<script>
    import { Router, Link } from "svelte-routing";
    export let url = "";
</script>
<!-- +++++ end +++++ -->
<!-- end -->
<!-- +++++ html +++++ -->
<header class="header">
    <ul class="header_list">
        <Router {url}>
            <li class="header_item">
            <Link to="/">Home</Link>
            </li>
            <li class="header_item">
            <Link to="/countrylist">CountryList</Link>
            </li>
            <li class="header_item">
            <Link to="/opinion">Opinion</Link>
            </li>
        </Router>
    </ul>
</header>
<!-- +++++ end +++++ -->
<!-- +++++ css +++++ -->
<style>
    .header {
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 16px;
    }
    
    .header_list {
        display: flex;
    }

    .header_item:not(:first-child) {
        margin-left: 24px;
    }
</style>
<!-- +++++ end +++++ -->