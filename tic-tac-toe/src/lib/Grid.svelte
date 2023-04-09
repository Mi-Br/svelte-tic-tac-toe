<script>
  import Square from "./Square.svelte";
  // import { CheckWinner } from "./Helper.svelte";
  let board = Array(9).fill(null);
  let winner = false;
  //  TODO: add event log
  //  TODO: stop game once all turns end

  let xTurn = true;
  function handleSquareClick(event) {
    console.log("try");
    if (!winner) {
      const i = event.detail.id;
      let nextBoard = board.slice();
      nextBoard[i] = xTurn ? "X" : "O";
      board = nextBoard;
      xTurn = !xTurn;
    }
    winner = CheckWinner(board);
    if (winner == true) {
      let player = xTurn ? "O" : "X";
      alert("we got winner:" + player);
    }
    console.log(CheckWinner(board));
  }

  const matrix = [
    [0, 1, 2],
    [3, 4, 5],
    [6, 7, 8],
    [0, 3, 6],
    [1, 4, 7],
    [2, 5, 8],
    [0, 4, 8],
    [2, 4, 6],
  ];

  const CheckWinner = (grid) => {
    return matrix.some(([a, b, c]) => grid[a] != null && grid[a] === grid[b] && grid[b] === grid[c]);
  };
</script>

<div class="grid">
  {#each board as b, index}
    <Square Value={b} Id={index} on:squareClicked={handleSquareClick} />
  {/each}
</div>

<style>
  .grid {
    display: grid;
    max-width: 243px;
    grid-template-columns: repeat(3, 1fr);
  }
</style>
