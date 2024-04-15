<script>
</script>

<main>
  <div class="card">
    <div class="card-header">
      <slot name="header">header</slot>
    </div>
    <div class="card-body">
      <slot name="body">
        <img src="./src/assets/svelte.svg" alt="Svelte" />
      </slot>
    </div>
    {#if $$slots.footer}
      <hr />
      <div class="card-footer">
        <slot name="footer">footer</slot>
      </div>
    {/if}
  </div>
</main>

<style>
  .card {
    box-shadow: 0 4px 8px 0 rgba(212, 96, 96, 0.783);
    transition: 0.3s;
    padding: 16px;
    margin-bottom: 20px;
    width: 200px;
  }

  .card:hover {
    box-shadow: 0 8px 16px 0 rgba(212, 96, 96, 0.783);
  }
</style>
