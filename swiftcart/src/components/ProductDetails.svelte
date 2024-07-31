<script>
  export let params;
  export let productList;

  // Find the product using the id from the URL parameters
  const product = productList.find(p => p.id == params.id);
</script>

{#if product}
  <div class="container mx-auto p-4">
    <h2 class="text-2xl font-bold">{product.title}</h2>
    <img src={product.image} alt={product.title} class="w-48 h-48 object-contain mb-4" />
    <p class="text-gray-500">{product.category}</p>
    <p class="text-gray-500">{`R${product.price}`}</p>
    <button class="bg-gray-500 text-white p-2 px-3 rounded mt-4">Add To Cart</button>
  </div>
{:else}
  <p>Product not found!</p>
{/if}
