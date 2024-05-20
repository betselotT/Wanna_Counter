<script>
	import Player from "./Player.svelte";
</script>

<main>
	<div class="wrapper">
		<div class="container">
			<h1>Choose a Game</h1>
			<div class="choices">
				<button class="c">Counter</button>
				<button class="c">#</button>
				<button class="c">#</button>
			</div>

		</div>
		<div class="counter">
			<h1>Counter Game</h1>
			<div class="options">
				<Player num={1} />
				<Player num={2} />
			</div>
		</div>
	</div>
</main>

<style>
	.container {
		border: 1px solid black;
		background-color: gray;
		width: 50%;
		text-align: center;
		margin-left: 25%;
		margin-top: 5%;
	}
	.choices {
  		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.c {
		padding: 10px;
		margin: 5px;
	}
</style>