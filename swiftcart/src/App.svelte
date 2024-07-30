<script>
  import NavBar from './components/NavBar.svelte';
  import Footer from './components/Footer.svelte';
  import ProductCard from './components/ProductCard.svelte';
  import ProductDetails from './components/ProductDetails.svelte';
  import { onMount } from 'svelte';

  let products = [];
  let selectedProduct = null;
  let loading = false;

  onMount(async () => {
    const response = await fetch('/api/products');
    products = await response.json();
  });

  function selectProduct(product) {
    loading = true;
    setTimeout(() => {
      selectedProduct = product;
      loading = false;
    }, 1000); // Simulate a delay for loading animation
  }

  function goBack() {
    selectedProduct = null;
  }
</script>

<NavBar />

<main>
  {#if loading}
    <div class="loading-ring"></div>
  {:else if selectedProduct}
    <ProductDetails {selectedProduct} on:goBack={goBack} />
  {:else}
    <div class="product-grid">
      {#each products as product}
        <div on:click={() => selectProduct(product)}>
          <ProductCard {product} />
        </div>
      {/each}
    </div>
  {/if}
</main>

<Footer />

<style>
  main {
    background-color: #f0f0f0;
    padding: 16px;
    min-height: calc(100vh - 64px); /* Adjust based on navbar height */
  }

  .product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 20px;
  }

  .product-grid > div {
    cursor: pointer;
  }

  .loading-ring {
    display: inline-block;
    width: 80px;
    height: 80px;
  }
  .loading-ring:after {
    content: " ";
    display: block;
    width: 64px;
    height: 64px;
    margin: 8px;
    border-radius: 50%;
    border: 6px solid #007bff;
    border-color: #007bff transparent #007bff transparent;
    animation: loading-ring 1.2s linear infinite;
  }
  @keyframes loading-ring {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(360deg);
    }
  }
</style>


