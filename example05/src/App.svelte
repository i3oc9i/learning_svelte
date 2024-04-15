<script>
  import External from "./lib/External.svelte";

  let internal_msg = "";
</script>

<main>
  <h1>Event Forwarding</h1>
  <External on:click_me_event={(event) => (internal_msg = event.detail)} />
  <h2>{internal_msg}</h2>
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
