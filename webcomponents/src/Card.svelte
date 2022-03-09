<svelte:options tag="my-card" />

<script>
	export let title;
</script>

<div class="card">
    <div class="title">{title}</div>
    <div class="content">
        <slot></slot>
    </div>
</div>

<style>
    .content{
        padding:10px;
    }
	.card{
         box-shadow: 0 3px 10px rgba(0, 0, 0, 0.541);
         width:1000px;
         margin:auto;
         margin-bottom: 20px;
         min-height: 200px;
         background-color: aliceblue;
    }

    .title{
        background-color: rgb(0, 0, 0);
        height:50px;
        text-align: center;
        color:white;
        padding:auto;
        display: flex;
        align-items: center;
        justify-content: center
    }
</style>