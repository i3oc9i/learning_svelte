<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let id;
  export let title;
  export let description;
  export let price;

  let buy_event = () => {
    dispatch("buy_event", { id });
  };
</script>

<main>
  <div class="card w-96 bg-base-100 shadow-xl">
    <div class="card-body">
      <h2 class="card-id">{id}</h2>
      <h2 class="card-title">{title}</h2>
      <p>{description}</p>
      <p>{price}</p>
      <div class="card-actions justify-end">
        <button class="btn btn-primary" on:click={buy_event}>Buy</button>
      </div>
    </div>
  </div>
</main>

<style>
</style>
