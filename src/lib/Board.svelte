<script>
  import Column from "./Column.svelte";
  
  let columns = [
    {name: "Kvetches", items: [{id: 1, content: "This is a kvetch"}]},
    {name: "Appreciations", items: [{id: 2, content: "This is an appreciation"}]},
    {name: "Flaws", items: [{id: 3, content: "This is a flaw"}]},
    {name: "Experiments", items: [{id: 4, content: "This is an experiment"}]},
  ]
</script>

<section class="section container">
  <div class="columns">
    {#each columns as {name, items} (name)}
    <Column items="{items}" name="{name}"></Column>
    {/each}
  </div>
</section>