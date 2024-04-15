<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();
</script>

<main>
  <div class="absolute top-0 left-0 right-0 flex justify-center">
    <div class="bg-gradient-to-r from-purple-300 to-purple-500 p-5 rounded-lg">
      <h2 class="pb-5">This is a Popup</h2>
      <button
        class="btn btn-outline btn-primary"
        on:click={() => {
          dispatch("close_popup_event");
        }}>Close</button
      >
    </div>
  </div>
</main>
