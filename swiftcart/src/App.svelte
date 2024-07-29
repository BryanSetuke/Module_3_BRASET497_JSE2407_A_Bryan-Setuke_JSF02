<script>
  import { Router, Route } from 'svelte-routing';
  import NavBar from './components/NavBar.svelte';
  import Home from './routes/index.svelte';
  import ProductDetail from './routes/product/[id].svelte';
</script>

<NavBar />

<Router>
  <Route path="/" component={Home} />
  <Route path="product/:id" component={ProductDetail} />
</Router>

<style>
  main {
    padding: 16px;
  }
</style>
