<script>
  let maxClick = $state(4);
  let cnt = $state(4);

  function onClick() {
    if (cnt > 0) {
      cnt -= 1;
    }
  }
</script>

<h1>Daniel Tetteh's VIS Site</h1>
<img
  width="200px"
  src="https://upload.wikimedia.org/wikipedia/commons/9/94/Morning_view_of_the_downtown_skyline_from_near_Morgan_Point_along_Lakefront_Trail%2C_Chicago%2C_2025.jpg"
/>
<div>
  You can click up to
  <select
    bind:value={maxClick}
    onchange={() => (cnt = maxClick)}>
    {#each [2, 4, 6] as optionNum}
      <option value={optionNum}>
        {optionNum}
      </option>
    {/each}
  </select>
  times
</div>
<button onclick={onClick}> Click Me </button>

{#if cnt > 0}
  <p id="info">Remaining Number of Clicks: {cnt}</p>
{:else}
  <p>No more clicks allowed</p>
{/if}

<style>
  body {
    font-family: Arial, Helvetica, sans-serif;
  }
  button {
    background-color: #44aa66;
    color: white;
    font-size: xx-large;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
  }
</style>