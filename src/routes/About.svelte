<script>
import Home from './Home.svelte'
import Form from './Components/Form.svelte'
import Login from './Components/Login.svelte'
import Story from './Components/Story.svelte';
import WebExpertise from './Components/WebExpertise.svelte';
import Hobbies from './Components/Hobbies.svelte';
import Testimonials from './Components/Testimonials.svelte';


const options = [
		{ name: 'story',   component: Story},
		{ name: 'web', component: WebExpertise},
		{ name: 'hobbies',  component: Hobbies },
{ name: 'testimonials',  component: Testimonials },
	];

let selected = options[0];

</script>


<style>
	.container-area {
		animation-name: animateappear;
  		animation-duration: 1s;
  		animation-fill-mode: both;;
	}
	.container { min-width: 600px; height: 600px; display: block; flex-wrap: wrap; border: 1px solid black; text-align: center; position: relative; animation-name: animateappear;
  animation-duration: 1s;
  animation-fill-mode: both;}
.container {
		background: linear-gradient(to top left, rgba(111, 96, 161, 0.39), rgba(197, 171, 177, 0.267));
		box-shadow: 1px 1px 3px 1px black;
	}
	

	.select-div {
		display: block;
		padding: 1.2rem;
		margin-right: 12rem;
		max-width: 240px;
		animation-name: animateappear;
  animation-duration: 1s;
  animation-fill-mode: both;
	}
	@media (min-width: 640px) {
		.container {
			max-width: none;
		}
	}


</style>
<Home />
<!-- <div class="">
	<select bind:value={selected}>
	{#each options as option}
		<option value={option}>{option.name}</option>
	{/each}
</select>
</div> -->
<div class="container-area">
<select bind:value={selected} class="ui vertical dropdown menu select-div">
	{#each options as option}
		<option value={option}>{option.name}</option>
	{/each}
</select>
</div>
<div class="container">

{#if selected.name=== 'story'}
	<Story />
{:else if selected.name=== 'web'}
	<WebExpertise />
{:else if selected.name=== 'hobbies'}
	<Hobbies />
{:else if selected.name=== 'testimonials'}
	<Testimonials />
{/if}
</div>
<Form />