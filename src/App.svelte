<script>
  // @ts-ignore
  import { Router, Route } from "svelte-routing";
  import Home from "./routes/Home.svelte";
  import CountryList from "./routes/CountryList.svelte";
  import Opinion from "./routes/Opinion.svelte";
  export let url = "";
</script>
<Router {url}>
  <div>
    <Route path="/" component={Home}/>
    <Route path="/countrylist" component={CountryList} />
    <Route path="/opinion" component={Opinion} />
  </div>
</Router>

