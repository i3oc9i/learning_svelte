<script>
  import { P } from "flowbite-svelte";
  import { Link } from "svelte-routing";
</script>

<main>
  <Link to="/articles">
    <P
      class="w-full flex justify-center mb-6 text-lg lg:text-xl sm:px-16 xl:px-20 text-orange-400 dark:text-orange-300"
      >Discover the list of articles.</P
    >
  </Link>
</main>
