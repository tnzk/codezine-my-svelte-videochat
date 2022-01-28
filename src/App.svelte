<script lang="ts">
	import Participant from './Participant.svelte'
	let visible = true;
	let audio = true;
	
	let participantNames = [ '参加者猫 (2)', '参加者猫 (3)', '参加者猫 (4)'];
	let nextParticipant;
	setInterval(() => {
		nextParticipant = `参加者猫(${participantNames.length+2})`;
	}, 5000)
	const handleApprove = () => {
		participantNames = [...participantNames, nextParticipant];
		nextParticipant = undefined;
	};
	$: numParticipants = participantNames.length + 1;
	const handleNoImpl = () => alert('実装していません。実装してみてください！');
</script>
{#if nextParticipant}
	<div id="popup">
		「{nextParticipant}」が待機中
		<button on:click={handleApprove}>入室許可</button>
	</div>
{/if}
<div>参加者数: {numParticipants}</div>
<div class="participant p1">
	<span>
		参加者猫 (1) (自分)
		{#if audio}
			🔉
		{:else}
			🔇
		{/if}
	</span>
	{#if visible}
		<img src="https://placekitten.com/320/240?image=1">
	{:else}
		<img src="https://via.placeholder.com/320x240/000000/FFFFFF/?text=Video%20OFF">
	{/if}
</div>
{#each participantNames as name, index}
	<Participant {name} catType={index} />
{/each}
<div class="list-of-participants">
	<ul>
		<li>参加者猫 (1) (自分)</li>
		{#each participantNames as name}
			<li>{name}</li>
		{/each}
	</ul>
</div>
<div class="control">
	<button on:click={handleNoImpl}>退出</button>
	<button on:click={() => audio = !audio}>音声 OFF</button>
	<button on:click={() => visible = !visible}>ビデオ ON/OFF</button>
	<button on:click={handleNoImpl}>画面共有</button>
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