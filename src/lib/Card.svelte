<script>
  import CodeMirror from "./CodeMirror.svelte";
//import HyperMd from "./HyperMD.svelte";

    export let content = ""
</script>

<div class="card">
  <div class="card-content">
    <div class="content is-size-7">
      <CodeMirror bind:value="{content}" />
      <br />
      <p>:{content}</p>
      <time datetime="2016-1-1">11:09 PM - 1 Jan 2016</time>
    </div>
  </div>
</div>
