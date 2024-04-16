<script>
  import { Input, Heading, Textarea, Button, Alert } from "flowbite-svelte";
  import { InfoCircleSolid } from "flowbite-svelte-icons";

  import { articleList } from "../store/article";

  let infoAllert = false;

  let article = {
    title: "",
    abstract: "",
    text: "",
  };

  let add_article = () => {
    if (!article.title || !article.abstract || !article.text) {
      infoAllert = true;
      return;
    }

    const newArticle = {
      id: Date.now().toString(),
      title: article.title,
      abstract: article.abstract,
      text: article.text,
    };
    articleList.update((articles) => [...articles, newArticle]);

    article = {
      title: "",
      abstract: "",
      text: "",
    };
  };
</script>

<main>
  {#if infoAllert}
    <Alert dismissable on:close={() => (infoAllert = false)} color="blue">
      <InfoCircleSolid slot="icon" class="w-5 h-5" />
      <span class="font-medium">Please, </span>
      fill allthe fiedls and try submitting again.
    </Alert>
  {/if}

  <form on:submit|preventDefault={add_article}>
    <Heading align="left" tag="h3" class="mb-3">Add new article</Heading>
    <div class="mb-2">
      <Input
        type="text"
        id="new-title"
        placeholder="insert title ..."
        size="md"
        bind:value={article.title}
      />
    </div>
    <div class="mb-2">
      <Textarea
        id="new-abstract"
        placeholder="insert abstract ..."
        rows="3"
        bind:value={article.abstract}
      />
    </div>
    <div class="mb-2">
      <Textarea
        id="new-text"
        placeholder="insert article ... "
        rows="7"
        bind:value={article.text}
      />
    </div>
    <Button type="submit">Submit</Button>
  </form>
</main>
