<script>
	import Player from "./Player.svelte";
	let playerOne = 0;
	let playerTwo = 0;
	$: oneWon = playerOne == 10;
	$: twoWon = playerTwo == 10;
	$: gameOver = oneWon || twoWon;

	function updateOne(e) {
		const update = e.detail;
		playerOne += update;
	}

	function updateTwo(e) {
		const update = e.detail;
		playerTwo += update;
	}

	function again() {
		playerOne = 0;
		playerTwo = 0;
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
				<Player fontColor="#0000AA" on:points={updateOne} won={oneWon} winner="Player One Won!" {gameOver} num={1} score={playerOne} />
				<Player fontColor="#AA0000" on:points={updateTwo} won={twoWon} winner="Player Two Won!" {gameOver} num={2} score={playerTwo} />
			</div>
			<button on:click={again}>Play Again!</button>
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
	.options {
		display: flex;
		
	}
	.counter {
		padding: 20px;
	}
	.counter button {
		display: block;
		margin-top: 20px;
		border: solid salmon 1px;
		background-color: black;
		color: white;
		font-size: 20px;
		border-radius: 3px;
	}
	.counter button:hover {
		cursor: pointer;
	}
</style>