<script>
  import { Router, Route, Link } from "svelte-routing";
  import Home from "./lib/Home.svelte";
  import Blog from "./lib/Blog.svelte";
  import About from "./lib/About.svelte";

  let basepath = "/";

  $: url_path = location.pathname;
</script>

<main>
  <h1>Routing</h1>

  <div class="url">URL: {url_path}</div>

  <Router {basepath}>
    <nav>
      <div><Link to="/">Home</Link></div>
      <div><Link to="/blog">Blog</Link></div>
      <div><Link to="/about">About</Link></div>
    </nav>

    <div>
      <Route path="/" component={Home} />
      <Route path="/blog" component={Blog} />
      <Route path="/about" component={About} />
    </div>
  </Router>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    font-weight: 100;
  }

  :global(h1) {
    color: firebrick;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  :global(h2) {
    color: firebrick;
    text-transform: none;
    font-size: 2.5em;
    font-weight: 50;
  }

  .url {
    font-size: 1em;
    font-weight: 50;
    padding-bottom: 10px;
  }

  @media (min-width: 600px) {
    main {
      max-width: none;
    }
  }
</style>
