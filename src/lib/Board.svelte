<script>
  import Card from "./Card.svelte";
  
  let content = "This is a test"

  let cards = [
    {content: "This is a kvetch", column:"k"},
    {content: "This is an appreciation", column:"a"},
    {content: "This is a flaw", column:"f"},
    {content: "This is an experiment", column:"e"},
  ]

  function cardFilter(cardlist, column) {
    return cardlist.filter((v) => v.column == column)
  }
</script>

<section class="section container">
  <div class="columns">
    <div class="column">
      {#each cardFilter(cards, "k") as card}
        <Card bind:content="{card.content}" />
      {/each}
    </div>
    <div class="column">
      {#each cardFilter(cards, "a") as card}
        <Card bind:content="{card.content}" />
      {/each}
    </div>
    <div class="column">
      {#each cardFilter(cards, "f") as card}
        <Card bind:content="{card.content}" />
      {/each}
    </div>
    <div class="column">
      {#each cardFilter(cards, "e") as card}
        <Card bind:content="{card.content}" />
      {/each}
    </div>
  </div>
</section>