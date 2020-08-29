<script>
    import Home from './Home.svelte'
  import { onMount } from 'svelte'

  export let params

  const apiUrl = 'https://jsonplaceholder.typicode.com/posts/'
  let data = []

  onMount(async () => {
    const response = await fetch(apiUrl + params.id)
    data = await response.json()
  });
</script>
<Home />

<h1>{data.title}</h1>
<p>{data.body}</p>