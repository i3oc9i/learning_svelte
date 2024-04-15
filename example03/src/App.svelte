<script>
  import { setContext } from "svelte";
  import ComponentC from "./lib/ComponentC.svelte";

  const username = "i3oc9i";

  setContext("app_ctx", username);
</script>

<main>
  <h1>Context API</h1>
  <h2>Username: {username}</h2>
  <ComponentC />
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
