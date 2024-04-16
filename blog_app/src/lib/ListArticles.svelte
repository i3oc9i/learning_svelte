<script>
  import { Link } from "svelte-routing";
  import { AccordionItem, Accordion } from "flowbite-svelte";

  import { articleList } from "../store/article";

  let articles = $articleList;
</script>

<main>
  {#if articles.length === 0}
    <p class="text-center text-gray-500 dark:text-gray-400">No articles.</p>
  {/if}
  {#each articles as article}
    <Accordion>
      <AccordionItem>
        <span slot="header">{article.title}</span>
        <p class="text-left mb-2 text-gray-500 dark:text-gray-400">{article.abstract}</p>
        <Link to="/articles/{article.id}">
          <p class="text-right mb-2 text-orange-400 dark:text-orange-300">Read more</p>
        </Link>
      </AccordionItem>
    </Accordion>
  {/each}
  {#if articles.length > 0}
    <p class="text-center text-gray-500 dark:text-gray-400 mt-3">No more articles found.</p>
  {/if}
</main>
