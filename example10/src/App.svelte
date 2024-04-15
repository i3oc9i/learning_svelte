<script>
  import Decrement from "./lib/Decrement.svelte";
  import Display from "./lib/Display.svelte";
  import Increment from "./lib/Increment.svelte";
  import Reset from "./lib/Reset.svelte";
</script>

<main>
  <h1>Svelte Store</h1>

  <Display />

  <div style="display: flex; justify-content: space-around;">
    <Increment />
    <Decrement />
    <Reset />
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    font-weight: 100;
  }

  :global(h1) {
    color: firebrick;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  :global(h2) {
    color: firebrick;
    text-transform: none;
    font-size: 2.5em;
    font-weight: 50;
  }

  @media (min-width: 600px) {
    main {
      max-width: none;
    }
  }
</style>
