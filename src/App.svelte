<script>
	import Player from "./Player.svelte";
	let num;
	let score;
	let playerOne = 5;
	let playerTwo = 5;

	function updateOne(e) {
		const update = e.detail;
		playerOne += update;
	}

	function updateTwo(e) {
		const update = e.detail;
		playerTwo += update;
	}

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
				<Player on:points={updateOne} num={1} score={playerOne} />
				<Player on:points={updateTwo} num={2} score={playerTwo} />
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