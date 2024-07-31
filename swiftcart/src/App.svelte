<script>
  import { onMount } from 'svelte';
  import { Router, Route } from 'svelte-routing';
  import NavBar from '../src/components/NavBar.svelte';
  import MainContent from '../src/components/MainContent.svelte';
  import ProductDetail from '../src/components/ProductDetails.svelte';

  let productList = [];
  let loading = true;

  // Fetching product data from the API
  onMount(async () => {
    const response = await fetch('https://fakestoreapi.com/products');
    productList = await response.json();
    loading = false;
  });
</script>

<NavBar />
<Router>
  <Route path="/" let:params>
    {#if loading}
      <p>Loading...</p>
    {:else}
      <MainContent {productList} />
    {/if}
  </Route>
  <Route path="product/:id" let:params>
    <ProductDetail {params} {productList} />
  </Route>
</Router>
