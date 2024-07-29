<script>
  import { onMount } from 'svelte';
  export let id;
  let product = null;
  let loading = true;

  onMount(async () => {
    const res = await fetch(`https://fakestoreapi.com/products/${id}`);
    product = await res.json();
    loading = false;
  });
</script>

{#if loading}
  <p>Loading...</p>
{:else}
  <div class="product-detail">
    <img src={product.image} alt={product.title} />
    <h2>{product.title}</h2>
    <p>Price: ${product.price}</p>
    <p>Category: {product.category}</p>
    <p>{product.description}</p>
    <p>Rating: {product.rating.rate} ({product.rating.count} reviews)</p>
    <button on:click={() => window.history.back()}>Back to Products</button>
  </div>
{/if}

<style>
  .product-detail {
    border: 1px solid #ddd;
    padding: 16px;
    text-align: center;
  }
  img {
    max-width: 100%;
    height: auto;
  }
</style>
