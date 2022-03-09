<script>
	export let name;
	let count = 0;

	function updateCount(){
		count++;
	}
</script>

<button on:click={updateCount} type="button">{name} - {count}</button>

<style>
	button {
		padding:10px;
		text-align: center;
		background-color: cornflowerblue;
		color:white;
	}
</style>