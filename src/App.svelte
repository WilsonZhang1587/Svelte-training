<script>
  import NavBar from "./Navebar.svelte"

  let name = "Jhon Doe";
  let points = 100;
  let showControls = false;

  const addPoint = () => (points += 1);
  const removePoint = () => (points -= 1);
</script>

<style>
  .container {
    width: 80%;
    margin: 0 auto;
  }
  .card-block {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 0px 16px;
    border: 1px solid #ccc;
  }
  h1 {
    color: #204f6e;
  }
</style>

<NavBar />
<div class="container">
  <div class="card">
    <div class="card-block">
      <div>
        <h1>{name}</h1>
        <h3>{points}</h3>
      </div>
      {#if showControls}
        <div>
          <button class="btn" on:click={addPoint}>+1</button>
          <button class="btn" on:click={removePoint}>-1</button>
        </div>
      {/if}
    </div>
    <input type="text" bind:value={points} />
  </div>
</div>
