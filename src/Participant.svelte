<script>
  export let name;
  export let catType;
  let video = true;
</script>

<div class="participant">
  <span on:click={() => video = !video}>{name}</span>
  {#if video}
    <img src="https://placekitten.com/320/240?image={catType+2}">
  {:else}
    <img src="https://via.placeholder.com/320x240/000000/FFFFFF/?text=Video%20OFF">
  {/if}
</div>

<style>
	.participant {
		position: relative;
		float: left;
		width: 320px;
		height: 240px;
		border: 1px solid black;
		margin: 2px;
		background: black;
	}
	.participant span {
		background: black;
		color: white;
		padding: 0 0.5rem;
		position: absolute;
		top: 0;
	}
</style>