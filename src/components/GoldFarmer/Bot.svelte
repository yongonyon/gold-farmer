<script>
  export let config;
  export let gold;
  export let clickValue;
  export let goldPerSecond;

  config.generating = 0;
  config.level = 0;

  function upgradeBot(n = 1) {
    for (let i = 0; i < n; i++) {
      if (gold - config.upgradeCost >= 0) {
        gold -= config.upgradeCost;
        config.upgradeCost += config.levelIncrease;
        config.level++;
        config.generating += config.baseGP;
        clickValue += config.clickIncrease;
        goldPerSecond += config.baseGP;
      }
    }
  }
</script>

<div class="card" style="margin: 10px;">
  <h5 class="card-header">{config.name}</h5>
  <div class="card-body">
    {config.level}
    <div class="row">
      <button
        class="btn btn-success"
        style="margin: 10px;"
        on:click={() => upgradeBot()}>
        x1
      </button>
      <button
        class="btn btn-success"
        style="margin: 10px;"
        on:click={() => upgradeBot(10)}>
        x10
      </button>
      <button
        class="btn btn-success"
        style="margin: 10px;"
        on:click={() => upgradeBot(100)}>
        x100
      </button>
    </div>
    <div class="row">
      <div>GP/s: {config.generating}</div>
    </div>
    <div class="row">
      <div>Cost: {config.upgradeCost}</div>
    </div>
    <div class="row">
      <div>Base GP/sec: {config.baseGP}</div>
    </div>
  </div>
</div>
