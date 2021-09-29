<script>
  import CodeMirror from "./CodeMirror.svelte";
//import HyperMd from "./HyperMD.svelte";

    export let content = ""
    let textarea

    function setHeight(e){
      e.target.style.removeProperty('height');
      e.target.style.height = (this.scrollHeight+2) + 'px';
    }
</script>

<style>
  .card {
    margin-bottom: 1rem;
  }
  .textarea {
    overflow-y: hidden;
    border: none;
    background: white;
    box-shadow: none;
    resize: none;
  }
</style>

<div class="card">
  <div class="card-content">
    <div class="content is-size-7">
      <textarea class="textarea" bind:value="{content}" bind:this="{textarea}" on:keyup="{setHeight}" on:focus="{setHeight}" on:click="{setHeight}" />
      <br />
      <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
    </div>
  </div>
</div>
