<script>
  export let product;
</script>

<div class="product-card" on:click={() => window.location.href = `/product/${product.id}`}>
  <img src={product.image} alt={product.title} />
  <h2>{product.title}</h2>
  <p>Price: ${product.price}</p>
  <p>Category: {product.category}</p>
</div>

<style>
  .product-card {
    border: 1px solid #ddd;
    padding: 16px;
    text-align: center;
    cursor: pointer;
  }
  img {
    max-width: 100%;
    height: auto;
  }
</style>
