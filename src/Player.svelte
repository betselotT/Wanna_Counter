<script>
    import { createEventDispatcher } from "svelte";
    export let num;
    export let score;
    const dispatch = createEventDispatcher();

    function plus() {
        dispatch("points", 1);
    }

    function minus() {
        dispatch("points", -1);
    }
</script>
<main>
    <h3>Player {num}</h3>
    <h2>Score -> {score}</h2>
    <button on:click={plus}>+</button>
    <button on:click={minus}>-</button>
</main>