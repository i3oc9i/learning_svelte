<script>
  import { count } from "../store/count.js";

  $: double = $count * 2;
</script>

<main>
  <h2>Counter: {$count} Double: {double}</h2>
</main>
