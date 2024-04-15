<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let click_me = () => {
    dispatch("click_me_event", "Hello from Internal");
  };
</script>

<main>
  <h2>Internal Component</h2>
  <button on:click={click_me}>Click me</button>
</main>
