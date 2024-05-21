<script>
    import { createEventDispatcher } from "svelte";
    export let num;
    export let score;
    export let fontColor;
    export let won;
    export let winner;
    export let gameOver;
    const dispatch = createEventDispatcher();

    function plus() {
        dispatch("points", 1);
    }

    function minus() {
        dispatch("points", -1);
    }
</script>

<main>
    <h3 style="color: {fontColor}">Player {num}</h3>
    <h2>Score -> {score}</h2>
    <button class="plus" on:click={plus} disabled={gameOver}>+</button>
    <button class="minus" on:click={minus} disabled={gameOver}>-</button>
    {#if won}
        <h2 style="color: seagreen">{winner}</h2>
    {/if}
</main>

<style>
    button[disabled] {
        background-color: gray;
        pointer-events: none;
    }
    button {
        font-size: 20px;
        border-radius: 3px;
        width: 40px;
        color: white;
        font-family: monospace;
        font-weight: bold;
    }
    .plus {
        background-color: seagreen;
    }
    .minus {
        background-color: brown;
    }
</style>