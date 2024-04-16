<script>
  import { Heading, P, Button } from "flowbite-svelte";
  import { Router, Link } from "svelte-routing";

  const basepath = "/";
</script>

<main>
  <div
    class="flex items-center justify-center py-4 md:py-8 flex-wrap gap-3 mb-3 mx-auto dark:text-gray-400"
  >
    <Heading tag="h1" class="mb-4" customSize="text-4xl font-extrabold  md:text-5xl lg:text-6xl "
      >SvelteRust Lab</Heading
    >
    <P
      class="w-full flex justify-center mb-6 text-lg lg:text-xl sm:px-16 xl:px-20 dark:text-gray-400"
      >The last news and the best practices about Svelte, Wasm, Rust and Tauri.</P
    >
    <Router {basepath}>
      <Link to="/"><Button>Home</Button></Link>
      <Link to="/articles"><Button>Articles</Button></Link>
      <Link to="/add"><Button>Add</Button></Link>
    </Router>
  </div>
</main>
