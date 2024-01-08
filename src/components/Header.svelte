<!-- +++++ js +++++ -->
<script>
</script>
<!-- +++++ end +++++ -->
<!-- end -->
<!-- +++++ html +++++ -->
<header class="header">
    <ul class="header_list">
        <li class="header_item">
            <a href="/">home</a>
        </li>
        <li class="header_item">
            <a href="/">coutry list</a>
        </li>
        <li class="header_item">
            <a href="/">opinion</a>
        </li>
    </ul>
    <div class="search_box">
        <input type="text" placeholder="input this..." class="">
        <button type="submit">
            search
        </button>
    </div>
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

    .header_item:last-child {
        margin-right: 24px;
    }
</style>
<!-- +++++ end +++++ -->