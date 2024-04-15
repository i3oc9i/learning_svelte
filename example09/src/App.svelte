<script>
  import Counter, { total_count } from "./lib/Counter.svelte";
</script>

<main>
  <h1>Context Module</h1>
  <Counter />
  <Counter />
  <Counter />

  <hr />
  <div>
    <button
      on:click={() => {
        alert(`Total count is now: ${total_count}`);
      }}
    >
      total count
    </button>
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
