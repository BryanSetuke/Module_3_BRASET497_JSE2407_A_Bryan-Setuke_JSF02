<script>
  import ProductCard from './ProductCard.svelte';
  export let products = [];
</script>

<div class="product-grid">
  {#each products as product}
    <ProductCard {product} />
  {/each}
</div>

<style>
  .product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 16px;
  }
</style>

