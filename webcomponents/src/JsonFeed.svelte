<svelte:options tag="json-feed" />

<script> 
        export let path;
        let data = getNews();
        console.log(path);

   async function getNews() {
		const res = await fetch(path);
		const text = await res.text();
                let json = JSON.parse(text);
                console.log(json.items);
		if (res.ok) {
			return json.items;
		} else {
			throw new Error(text);
		}
    }
</script>

<link href="/main.css" rel="stylesheet">


{#await data}
        <div>Loading</div>
{:then data}
        {#each data as item, i}
        <div class="w-full m-auto shadow-lg mb-10">
                <div class="p-4 text-center text-lg bg-secondary text-white">
                        <h2 class='text-xl'>{item.title}</h2>
                </div>
                <div class="flex text-xl">
                        <img alt="decorative news image {i}" class="w-64" src="{item.image}" />
                        <div class="p-4">
                                {@html item.content_html}
                        </div>
                </div>
        </div>
        {/each}
{:catch data}
         <div>error</div>
{/await}

