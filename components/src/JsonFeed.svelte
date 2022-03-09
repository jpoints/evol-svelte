<script> 
        export let path;
        let data = getNews();

   async function getNews() {
		const res = await fetch(path);
		const text = await res.text();
                let json = JSON.parse(text);
		if (res.ok) {
			return json.items;
		} else {
			throw new Error(text);
		}
    }
</script>

{#await data}
        <div>Loading</div>
{:then data}
        {#each data as item, i}
        <div class="w-full m-auto shadow-xl m-8">
                <div class="p-4 text-center text-xl bg-blue-900 text-white">
                        <h2>{item.title}</h2>
                </div>
                <div class="flex text-xl">
                        <img class="w-64" src="{item.image}" />
                        <div class="p-4">
                                {@html item.content_html}
                        </div>
                </div>
        </div>
        {/each}
{:catch data}
         <div>error</div>
{/await}

