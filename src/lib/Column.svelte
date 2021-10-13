<style>
  
  :global(.dragged) {
    pointer-events: none;
    z-index: 100;
    opacity: 0.3;
	}
	:global(.droptarget, .droptarget) {
    border: 1px dotted #666;
	}
</style>
<script>
  import {draggable} from './dragdrop.js'
  import Card from './Card.svelte';
  import {crossfade} from 'svelte/transition'
  import {quintOut, elasticOut} from 'svelte/easing'
  import { flip } from 'svelte/animate';

  const flipDurationMs = 200;
  
  export let items = []
  export let name = "Unnamed"

  function addToColumn(item) {
    items.push(item)
    items = items
  }

  function removeFromColumn(item) {
    items = items.filter(i => i.id != item.id)
  }
    
  const [send, receive] = crossfade({
    duration: d => 600,
    easing: elasticOut,
    fallback(node, params) {
      const style = getComputedStyle(node);
      const transform = style.transform === 'none' ? '' : style.transform;
      
      return {
        duration: 600,
        easing: quintOut,
        css: t => `
        transform: ${transform} scale(${t});
        opacity: ${t}
        `
      };
    }
  });

</script>
<section class="column column-dropaarea" on:drop={(e) => addToColumn(e.detail)}>
  <h2 class="subtitle is-5">{name}</h2>
  <div class="column-content">
    {#each items as item(item.id)}
    <div class="card dragthing" use:draggable={{data: item, targets: ['.card', '.column-dropaarea']}}
    on:dropped={(e) => removeFromColumn(e.detail.data)}>
      <Card bind:item></Card>
    </div>
    {/each}
  </div>
</section>