<script context="module">
  export async function load({ params }) {
    const res = await fetch(`https://fakestoreapi.com/products/${params.id}`);
    const product = await res.json();
    return {
      props: {
        product
      }
    };
  }
</script>

<script>
  export let product;
</script>

<div class="product-detail">
  <img src={product.image} alt={product.title} />
  <h2>{product.title}</h2>
  <p>Price: ${product.price}</p>
  <p>Category: {product.category}</p>
  <p>{product.description}</p>
  <p>Rating: {product.rating.rate} ({product.rating.count} reviews)</p>
  <button on:click={() => window.history.back()}>Back to Products</button>
</div>

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
