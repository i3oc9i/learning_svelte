<script>
  import { count } from "../store/count.js";

  function reset() {
    count.set(0);
  }
</script>

<main>
  <button on:click={reset}>reset</button>
</main>
