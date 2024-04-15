<script>
  import { count } from "../store/count.js";

  function decrement() {
    count.update((n) => n - 1);
  }
</script>

<main>
  <button on:click={decrement}>-</button>
</main>
