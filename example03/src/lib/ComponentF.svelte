<script>
  import { getContext, setContext } from "svelte";

  const username = getContext("app_ctx");
</script>

<main>
  <h2>F Component Username: {username} from App</h2>
</main>

<style>
</style>
