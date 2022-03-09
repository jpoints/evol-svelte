<script>
	export let name;
	let count = 0;
	function counter(){
		count++;
	}
</script>

<button class="bg-blue-600 text-white p-4 active:bg-blue-600" on:click={counter} type="button">{name} {count}</button>

<style>
</style>