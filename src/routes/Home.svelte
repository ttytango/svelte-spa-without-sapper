<script>
	import { onMount } from "svelte";
    


</script>

<div class="container">
	<h1>Tim's Blog</h1>
	
</div>

<style>
h1 {
	color: purple;
	font-family: 'kalam';
}
.container {
	display: grid;
	grid-template-columns: repeat(auto-fill, minmax(305px, 1fr));
	grid-gap: 15px;
}
.container > .card img {
	max-width: 100%;
}

</style>