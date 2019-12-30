<script>
  import Bot from "./Bot.svelte";

  export let gold;
  export let clickValue;
  export let goldPerSecond;

  let bots = [
    {
      name: "Flax Picker Pro",
      upgradeCost: 150,
      baseGP: 1,
      levelIncrease: 6,
      clickIncrease: 1
    },
    {
      name: "Woodcutting Bot",
      upgradeCost: 300,
      baseGP: 4,
      levelIncrease: 12,
      clickIncrease: 2
    },
    {
      name: "Dragon Fighter",
      upgradeCost: 500,
      baseGP: 7,
      levelIncrease: 20,
      clickIncrease: 3
    },
    {
      name: "Wyvern Slayer",
      upgradeCost: 750,
      baseGP: 11,
      levelIncrease: 30,
      clickIncrease: 5
    },
    {
      name: "Auto-Runecrafter",
      upgradeCost: 900,
      baseGP: 15,
      levelIncrease: 36,
      clickIncrease: 10
    }
  ];
</script>

<h1>Shop</h1>

<h3>GP: {gold}</h3>

<br />

<div class="row">
  {#each bots as bot}
    <Bot bind:config={bot} bind:gold bind:clickValue bind:goldPerSecond />
    <hr />
  {/each}
</div>
