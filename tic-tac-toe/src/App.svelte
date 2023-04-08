<script>
  import Square from "./lib/Square.svelte";

  let squares = Array(9).fill(false);
</script>

<main>
  {#each squares as square, index}
    <Square Value={square} id={index} />
  {/each}
</main>

<style>
  .row {
    display: flex;
  }
</style>
