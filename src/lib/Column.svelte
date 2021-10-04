<style>
  
  .dndzone {
    min-height: 12em
  }
</style>
<script>
  import {dndzone} from 'svelte-dnd-action';
  import {flip} from 'svelte/animate';
  import Card from './Card.svelte';
  const flipDurationMs = 200;
  
  export let items = []
  export let name = "Unnamed"
  
  function handleSort(e) {
    items = e.detail.items;
  }
</script>
<section class="column">
  <h2 class="subtitle is-5">{name}</h2>
  <div class="dndzone" use:dndzone={{items, flipDurationMs}} on:consider={handleSort} on:finalize={handleSort}>
    {#each items as item(item.id)}
    <div animate:flip={{duration:flipDurationMs}}>
      <Card bind:content="{item.content}"></Card>
    </div>
    {/each}
  </div>
</section>