<script>
  import ProductCard from './ProductCard.svelte';
  export let products = [];
</script>

<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4 p-4">
  {#each products as product}
    <ProductCard {product} />
  {/each}
</div>

