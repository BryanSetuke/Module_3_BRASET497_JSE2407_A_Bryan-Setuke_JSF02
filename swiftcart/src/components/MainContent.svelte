<script>
  import ProductCard from './ProductCard.svelte';
  export let productList;
</script>

<div class="container mx-auto p-4 bg-gray-100 flex-grow">
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
    {#each productList as product (product.id)}
      <ProductCard {product} />
    {/each}
  </div>
</div>
