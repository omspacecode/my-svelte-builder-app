<!-- src/routes/[...catchall]/+page.svelte -->
<script>
    import { isPreviewing, Content } from "@builder.io/sdk-svelte";
    
    import ProductCard from '../../lib/ProductCard.svelte';
    import ProductList from '../../lib/ProductList.svelte';

    const CUSTOM_COMPONENTS = [
    {
    component:ProductList,
    name: 'ProductList',
    inputs: [],
    }

    ];

    
    const BUILDER_API_KEY = "ae60598a419b4f32ba191072330010c0";
    // this data comes from the function in `+page.server.js`, which runs on the server only
    export let data;
  
    // show unpublished content when in preview mode.
    const canShowContent = data.content || isPreviewing();
  </script>

  <main>
    <h1>Welcome to SvelteKit</h1>
    <h2>Below is your Builder Content:</h2>
    <!-- TO DO: Add your Public API Key in <Content/>-->
    {#if canShowContent}
      <div>page Title: {data.content?.data?.title || "Unpublished"}</div>
      <Content
        model="page"
        content={data.content}
        apiKey={BUILDER_API_KEY}
        customComponents={CUSTOM_COMPONENTS}
      />
    {:else}
      Content Not Found
    {/if}
  </main>
  