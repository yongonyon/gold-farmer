<script>
  import Shop from "./../components/GoldFarmer/Shop.svelte";

  let gold = 100000;
  let clickValue = 1;
  let goldPerSecond = 0;

  function getGold() {
    gold += clickValue;
  }

  function doubleGold() {
    gold *= 2;
  }

  function resetGold() {
    gold = 0;
  }

  function chuckIt() {
    Math.floor(Math.random() * 2) ? doubleGold() : resetGold();
  }

  function farmGold() {
    setTimeout(() => {
      gold += goldPerSecond;
      farmGold();
    }, 1000);
  }

  farmGold();
</script>

<div class="card">
  <h1 class="card-header">Gold Farming</h1>
  <div class="card-body">
    <h4>GP/s: {goldPerSecond}</h4>
    <h4>GP/click: {clickValue}</h4>
  </div>
</div>

<div class="row">
  <button class="btn btn-primary" style="margin: 10px" on:click={getGold}>
    Click for GP!
  </button>
  <button class="btn btn-primary" style="margin: 10px" on:click={chuckIt}>
    Chuck It!
  </button>
</div>

<hr />

<Shop bind:gold bind:clickValue bind:goldPerSecond />
