<script>
  import { onMount } from 'svelte';
  import ProductGrid from '../components/ProductGrid.svelte';

  let products = [];
  let filteredProducts = [];
  let categories = [];
  let selectedCategory = 'all';
  let sortOption = '';
  let loading = true;

  onMount(async () => {
    const res = await fetch('https://fakestoreapi.com/products');
    products = await res.json();
    filteredProducts = products;
    loading = false;

    const categoriesRes = await fetch('https://fakestoreapi.com/products/categories');
    categories = await categoriesRes.json();
  });

  function filterByCategory(category) {
    selectedCategory = category;
    if (category === 'all') {
      filteredProducts = products;
    } else {
      filteredProducts = products.filter(product => product.category === category);
    }
    sortProducts();
  }

  function sortProducts() {
    if (sortOption === 'low-to-high') {
      filteredProducts.sort((a, b) => a.price - b.price);
    } else if (sortOption === 'high-to-low') {
      filteredProducts.sort((a, b) => b.price - a.price);
    }
  }

  function applySort(option) {
    sortOption = option;
    sortProducts();
  }
</script>

<main>
  <h1>SwiftCart</h1>
  <div id="products">
    <div>
      <label for="category">Filter by Category:</label>
      <select id="category" on:change={(e) => filterByCategory(e.target.value)}>
        <option value="all">All</option>
        {#each categories as category}
          <option value={category}>{category}</option>
        {/each}
      </select>

      <label for="sort">Sort by Price:</label>
      <select id="sort" on:change={(e) => applySort(e.target.value)}>
        <option value="">Select</option>
        <option value="low-to-high">Low to High</option>
        <option value="high-to-low">High to Low</option>
      </select>
    </div>

    {#if loading}
      <p>Loading...</p>
    {:else}
      <ProductGrid products= {filteredProducts} />
    {/if}
  </div>

  <section id="contact">
    <h2>Contact Us</h2>
    <p>Feel free to reach out!</p>
  </section>
</main>

<style>
  main {
    padding: 16px;
  }
  div {
    margin-bottom: 16px;
  }
  section {
    margin-top: 50px;
  }
</style>

