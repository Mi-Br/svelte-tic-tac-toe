<script>
  export let Value;
  export let Id;
</script>

<div class="square" id={Id}>
  {Value}
</div>

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
