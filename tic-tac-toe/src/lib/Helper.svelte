<script>
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

  export const CheckWinner = (grid) => {
    return matrix.some(([a, b, c]) => grid[a] && grid[a] === grid[b] && grid[b] === grid[c]);
  };
</script>
