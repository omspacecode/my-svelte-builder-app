<!-- src/lib/ProductList.svelte -->
<script>
    import { onMount } from "svelte";
    import ProductCard from "./ProductCard.svelte";
  
    let products = [];
  
    onMount(async () => {
      const response = await fetch("https://dummyjson.com/products?limit=10&select=title,price");
      const data = await response.json();
      products = data.products;
    });
  </script>
  
  <div class="product-list">
    {#each products as product}
      <ProductCard title={product.title} price={product.price} />
    {/each}
  </div>
  
  <style>
    .product-list {
      display: flex;
      flex-wrap: wrap;
      gap: 1em;
    }
  </style>
  