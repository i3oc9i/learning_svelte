<script>
  import { Router, Route } from "svelte-routing";

  import Header from "./lib/Header.svelte";
  import Home from "./lib/Home.svelte";
  import ListArticles from "./lib/ListArticles.svelte";
  import AddArticle from "./lib/AddArticle.svelte";
  import DisplayArticle from "./lib/DisplayArticle.svelte";
  import Footer from "./lib/Footer.svelte";

  const basepath = "/";
</script>

<main>
  <Header />

  <Router {basepath}>
    <Route path="/" component={Home} />
    <Route path="/articles" component={ListArticles} />
    <Route path="/add" component={AddArticle} />
    <Route path="/articles/:id" let:params><DisplayArticle id={params.id} /></Route>
  </Router>

  <Footer />
</main>
