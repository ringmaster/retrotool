<script>
  import CodeMirror from "./CodeMirror.svelte";
  import {onMount} from "svelte";
  import { tick } from 'svelte';
  //import HyperMd from "./HyperMD.svelte";
  
  export let content = ""
  let editing = false
  let textarea, staticcard
  
  onMount(() => {
    setHeight()
  })
  
  function setHeight(){
    if(textarea){
    textarea.style.removeProperty('height');
    textarea.style.height = (textarea.scrollHeight+2) + 'px';
    }
    if(staticcard){
    staticcard.style.removeProperty('height');
    staticcard.style.height = (staticcard.scrollHeight+2) + 'px';
    }
  }

  async function blurCard(){
    editing = false
    await tick();
    setHeight()
  }
  async function focusCard(){
    editing = true
    await tick();
    setHeight()
    textarea.focus()
  }
</script>

<style>
  .card {
    margin-bottom: 1rem;
    background-color: #ffffdd;
  }
  .textarea {
    overflow-y: hidden;
    border: none;
    background: transparent;
    box-shadow: none;
    resize: none;
    min-height: 2rem;
  }
  .card-content {
    padding: 0px;
  }
</style>

<div class="card">
  <div class="card-content">
    <div class="content is-size-7">
      {#if editing}
      <div>
        <textarea class="textarea" bind:value="{content}" bind:this="{textarea}" on:keyup="{setHeight}" on:focus="{setHeight}" on:click="{setHeight}" on:blur="{blurCard}" />
      </div>
      {:else}
      <div class="textarea" on:click="{focusCard}" bind:this="{staticcard}">
        {content}
      </div>        
      {/if}
    </div>
  </div>
</div>
