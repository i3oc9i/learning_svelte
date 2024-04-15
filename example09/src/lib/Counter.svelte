<script context="module">
  export let total_count = 0;
</script>

<script>
  let count = 0;
  const increment = () => {
    count += 1;
    total_count += 1;
  };
</script>

<button on:click={increment}>
  count is {count}
</button>
