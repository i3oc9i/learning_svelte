<script>
  import ComponentA from "./lib/ComponentA.svelte";
  import ComponentB from "./lib/ComponentB.svelte";
  import ComponentC from "./lib/ComponentC.svelte";

  let active_component = ComponentA;
</script>

<main>
  <h1>SPA: Dynamic Components</h1>

  <button on:click={() => (active_component = ComponentA)}>A</button>
  <button on:click={() => (active_component = ComponentB)}>B</button>
  <button on:click={() => (active_component = ComponentC)}>C</button>

  <svelte:component this={active_component} />
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
