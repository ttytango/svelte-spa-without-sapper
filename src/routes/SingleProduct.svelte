<script>
    import Home from './Home.svelte'
    import { onMount } from 'svelte'

    export let params

    const prodApiUrl = 'http://127.0.0.1:8000/api/products/'
  let bata = []

  onMount(async () => {
    const response = await fetch(prodApiUrl + params.id)
    bata = await response.json()
  });
</script>
<Home />

<h1>{bata.name}</h1>
<p>{bata.description}</p>
<p>{bata.price}</p>