<script>
  import { Link } from "svelte-routing";

  import { Card, Button, Modal } from "flowbite-svelte";
  import { ExclamationCircleOutline } from "flowbite-svelte-icons";

  import { articleList } from "../store/article";

  export let id = ""; // id of the article to display

  let articles = $articleList;

  let article = articles.find((article) => article.id === id);

  let confirmDelete = false;

  let deleteArticle = () => {
    articleList.update((articles) => articles.filter((article) => article.id !== id));
  };
</script>

<main>
  <Modal bind:open={confirmDelete} size="xs" autoclose>
    <div class="text-center">
      <ExclamationCircleOutline class="mx-auto mb-4 text-gray-400 w-12 h-12 dark:text-gray-200" />
      <h3 class="mb-5 text-lg font-normal text-gray-500 dark:text-gray-400">
        Are you sure you want to delete this article?
      </h3>
      <Link to="/articles">
        <Button color="red" class="me-2" on:click={deleteArticle}>Delete</Button>
      </Link>
      <Button color="alternative">Cancel</Button>
    </div>
  </Modal>

  {#if article}
    <Card size="xl" padding="xl">
      <div class="w-80 mx-auto">
        <h5 class="text-center text-3xl mb-2 font-bold text-gray-900 dark:text-white">
          {article.title}
        </h5>
        <p class="text-center text-sm italic mb-5 text-gray-500 dark:text-gray-400">
          {article.abstract}
        </p>
      </div>

      <div class="w-full">
        <p class="text-left text-base mb-5 text-gray-500 dark:text-gray-400">
          {article.text}
        </p>
      </div>

      <div class="flex justify-between">
        <Link to="/articles">
          <p class="text-left text-orange-400 dark:text-orange-300">Back</p>
        </Link>
        <Button on:click={() => (confirmDelete = true)}>Delete ...</Button>
      </div>
    </Card>
  {:else}
    <p class="text-center text-gray-500 dark:text-gray-400">No article found.</p>
  {/if}
</main>
