<script>
  import Popup from "./lib/popup.svelte";

  let showPoup = false;

  let show_popup = () => {
    showPoup = true;
  };

  let close_popup = () => {
    showPoup = false;
  };
</script>

<main>
  <h1 class="pb-5">Event Dispatcher</h1>

  <button class="btb btn-outline btn-primary" on:click={show_popup}>Show Popup</button>

  {#if showPoup}
    <Popup on:close_popup_event={close_popup} />
  {/if}
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
