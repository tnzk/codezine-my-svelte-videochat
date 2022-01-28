<script lang="ts">
	let visible = true;
</script>

<div class="participant p1">
	<span>参加者猫 (1) (自分)</span>
	{#if visible}
		<img src="https://placekitten.com/320/240?image=1">
	{:else}
		<img src="https://via.placeholder.com/320x240/000000/FFFFFF/?text=Video%20OFF">
	{/if}
</div>
<div class="participant">
	<span>参加者猫 (2)</span>
	<img src="https://placekitten.com/320/240?image=2">
</div>
<div class="participant">
	<span>参加者猫 (3)</span>
	<img src="https://placekitten.com/320/240?image=3">
</div>
<div class="participant">
	<span>参加者猫 (4)</span>
	<img src="https://placekitten.com/320/240?image=4">
</div>
<div class="list-of-participants">
	<ul>
		<li>参加者猫 (1) (自分)</li>
		<li>参加者猫 (2)</li>
		<li>参加者猫 (3)</li>
		<li>参加者猫 (4)</li>
	</ul>
</div>
<div class="control">
	<button>退出</button>
	<button>音声 OFF</button>
	<button on:click={() => visible = !visible}>ビデオ ON/OFF</button>
	<button>画面共有</button>
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
	.list-of-participants {
		clear: both;
	}
</style>