<script>
  import { createEventDispatcher } from 'svelte';
  import { faHeart, faCartPlus, faArrowLeft } from '@fortawesome/free-solid-svg-icons';
  import { FontAwesomeIcon } from '@fortawesome/svelte-fontawesome';
  export let selectedProduct;

  const dispatch = createEventDispatcher();

  function addToWishlist() {
    // Logic to add the product to the wishlist
  }

  function addToCart() {
    // Logic to add the product to the cart
  }

  function goBack() {
    dispatch('goBack');
  }
</script>

<div class="product-details">
  <div class="product-image">
    <img src={selectedProduct.image} alt={selectedProduct.title} />
  </div>
  <div class="product-info">
    <button on:click={goBack}>
      <FontAwesomeIcon icon={faArrowLeft} /> Go Back
    </button>
    <h1>{selectedProduct.title}</h1>
    <p>Price: ${selectedProduct.price}</p>
    <p>Category: {selectedProduct.category}</p>
    <p>Rating: {selectedProduct.rating}</p>
    <p>{selectedProduct.description}</p>
    <div class="actions">
      <button on:click={addToCart}>
        <FontAwesomeIcon icon={faCartPlus} /> Add to Cart
      </button>
      <button on:click={addToWishlist}>
        <FontAwesomeIcon icon={faHeart} /> Wishlist
      </button>
    </div>
  </div>
</div>

<style>
  .product-details {
    display: flex;
    padding: 20px;
    gap: 20px;
  }

  .product-image {
    flex: 1;
  }

  .product-image img {
    width: 100%;
    height: auto;
  }

  .product-info {
    flex: 2;
  }

  .product-info button {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 10px;
    border-radius: 4px;
    cursor: pointer;
    display: flex;
    align-items: center;
    margin-bottom: 10px;
  }

  .product-info button:hover {
    background-color: #0056b3;
  }

  .product-info button :global(svg) {
    margin-right: 5px;
  }

  .actions {
    display: flex;
    gap: 10px;
  }
</style>
