<script>
import Home from './Home.svelte'
import { onMount } from 'svelte'
import { has_prop } from 'svelte/internal'

  const apiUrl = 'https://jsonplaceholder.typicode.com/posts/'
  let data = []

  onMount(async () => {
    const response = await fetch(apiUrl)
    data = await response.json()
  });
</script>
<Home />

<h1>Blog</h1>

{#each data as item }
<div>
  <h5><a href="/blog/{item.id}">{item.title}</a></h5>
</div>
{/each}