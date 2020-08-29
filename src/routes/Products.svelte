<script>
import Home from './Home.svelte'
import { onMount } from 'svelte'
import { has_prop } from 'svelte/internal'

  const prodApiUrl = 'http://127.0.0.1:8000/api/products/'
  let bata = []

  onMount(async () => {
    const response = await fetch(prodApiUrl)
    bata = await response.json()
  });
</script>
<Home />

<h1>Products</h1>

{#each bata as product }
<div>
  <h5><a href="/products/{product.id}/">{product.name}</a></h5>
</div>
{/each}