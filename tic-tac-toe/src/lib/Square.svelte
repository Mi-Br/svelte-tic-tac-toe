<script>
  import { createEventDispatcher } from "svelte";
  export let Value;
  export let Id;
  const dispatch = createEventDispatcher();
  function handleClick(id) {
    dispatch("squareClicked", { id: id });
  }
</script>

<button class="square" id={Id} on:click={() => handleClick(Id)}>
  {#if Value != null}
    {Value}
  {/if}
</button>

<style>
  .square {
    width: 80px;
    height: 80px;
    margin: 1px;
    border: 1px solid white;
    text-align: center;
    padding: 1px;
    font-size: 50px;
  }
</style>
