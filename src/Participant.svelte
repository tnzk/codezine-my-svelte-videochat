<script>
  export let name;
  export let catType;
  let video;
</script>

<div class="participant">
  <span>{name}</span>
  <img src="https://placekitten.com/320/240?image={catType+2}">
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