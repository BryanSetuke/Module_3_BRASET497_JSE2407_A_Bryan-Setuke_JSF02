<script>
  import { Link } from 'svelte-routing';
  export let product;
</script>

<div class="border p-4 rounded-lg bg-white shadow-md flex flex-col h-80">
  <Link to={'/product/' + product.id} class="flex-grow">
    <img src={product.image} alt={product.title} class="w-full h-48 object-cover mb-2 rounded" />
  </Link>
  <h2 class="text-lg font-bold">{product.title}</h2>
  <p class="text-gray-500">{product.category}</p>
  <p class="text-gray-500">{`R${product.price}`}</p>
  <button class="bg-gray-500 text-white p-2 rounded mt-2 w-full hover:bg-gray-600 transition">Add To Cart</button>
</div>