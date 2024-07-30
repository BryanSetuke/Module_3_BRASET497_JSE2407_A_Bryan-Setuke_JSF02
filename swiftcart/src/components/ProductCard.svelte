<script>
  export let product;

  function addToCart() {
    // Logic to add the product to the cart
  }

  function addToWishlist() {
    // Logic to add the product to the wishlist
  }
</script>

<div class="product-card">
  <img src={product.image} alt={product.title} />
  <h3>{product.title}</h3>
  <p>Rating: {product.rating}</p>
  <button on:click|stopPropagation={addToCart}>Add to Cart</button>
  <button on:click|stopPropagation={addToWishlist}>♡</button>
</div>

<style>
  .product-card {
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 4px;
    padding: 16px;
    text-align: center;
  }

  .product-card img {
    max-width: 100%;
    height: auto;
  }

  .product-card button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 10px;
    border-radius: 4px;
    cursor: pointer;
    margin: 5px 0;
    display: block;
    width: 100%;
  }

  .product-card button:hover {
    background-color: #0056b3;
  }
</style>

