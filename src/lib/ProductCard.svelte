<!-- src/lib/ProductCard.svelte -->
<script>
    export let title;
    export let price;  </script>
  
  <div class="product-card">
    <h3>{title}</h3>
    <p>${price}</p>
  </div>
  
  <style>
    .product-card {
      border: 1px solid #ddd;
      padding: 1em;
      margin: 0.5em;
      border-radius: 5px;
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
    }
  
    h3 {
      margin: 0;
      font-size: 1.2em;
    }
  
    p {
      margin: 0.5em 0 0;
      font-size: 1em;
      color: #555;
    }
  </style>
  