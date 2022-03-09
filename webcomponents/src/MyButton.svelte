<svelte:options tag="my-button" />

<script>
	export let name;
	let count = 0;
	function counter(){
		count++;
	}
</script>

<button on:click={counter} type="button">{name} {count}</button>

<style>
	button{
		background-color:#6200EE;
		color:white;
		padding : 12px;
	}
</style>