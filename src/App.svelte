<script>
  import Navbar from "./lib/Navbar.svelte";
  import Steps from "./lib/Steps.svelte";
  import Board from "./lib/Board.svelte";
</script>
<svelte:head>
	<title>Retrotool</title>
  <link rel="icon" 
      type="image/png" 
      href="/retrotool_favicon.png">
</svelte:head>

<Navbar />

<Steps></Steps>

<Board></Board>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
</style>
