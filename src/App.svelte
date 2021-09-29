<script>
  import Navbar from "./lib/Navbar.svelte";
  import Card from "./lib/Card.svelte";

  let content = "This is a test"
</script>

  <Navbar />

  <main class="section container">
    <div class="columns">
      <div class="column">
        <Card bind:content="{content}" />
      </div>
      <div class="column">
        <Card bind:content="{content}"/>
      </div>
      <div class="column">
        <Card bind:content="{content}"/>
      </div>
    </div>
  </main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
