<script>
  import { Link } from 'svelte-routing';
  export let product;
</script>

<div class="cursor-pointer flex flex-col h-full bg-white border border-slate-200 shadow shadow-slate-950/5 rounded-2xl overflow-hidden transition-all duration-300 hover:-translate-y-1 hover:scale-105 hover:shadow-lg">
  <Link to={'/product/' + product.id} class="flex-grow">
    <img src={product.image} alt={product.title} class="w-full h-48 object-contain mt-4 mb-2 rounded" />
  </Link>
  <h2 class="text-lg font-bold px-2">{product.title}</h2>
  <p class="text-gray-500 px-2">{product.category}</p>
  <p class="text-gray-500 px-2">{`R${product.price}`}</p>
  <button class="inline-flex items-center justify-center mb-5 py-2 bg-[#354961] text-white text-sm font-medium rounded-md hover:bg-[#415a77] transition-colors duration-300">Add To Cart</button>
</div>