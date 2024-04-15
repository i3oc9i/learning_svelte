<script>
  import Card from "./lib/Card.svelte";
  let cardList = [
    {
      id: "P1",
      title: "Laptop",
      description: "A powerful laptop with high performance for work and entertainment.",
      price: 999.99,
    },
    {
      id: "P2",
      title: "Smartphone",
      description: "A feature-packed smartphone for staying connected on the go.",
      price: 699.99,
    },
    {
      id: "P3",
      title: "Headphones",
      description: "High-quality wireless headphones for immersive audio experience.",
      price: 199.99,
    },
    {
      id: "P4",
      title: "Tablet",
      description: "A versatile tablet for productivity and entertainment.",
      price: 499.99,
    },
    {
      id: "P5",
      title: "Smartwatch",
      description: "A stylish smartwatch with fitness tracking and notifications.",
      price: 299.99,
    },
  ];

  let handle_buy = (event) => {
    let id = event.detail.id;
    cardList = cardList.filter((card) => card.id !== id);
  };
</script>

<main>
  <h1>Our Products</h1>
  <h2>Shop now!</h2>

  <div class="flex flex-wrap -mx-4 justify-center">
    {#each cardList as card}
      <div class="card">
        <Card
          id={card.id}
          title={card.title}
          description={card.description}
          price={card.price}
          on:buy_event={handle_buy}
        />
      </div>
    {/each}
  </div>
</main>

<style>
  .card {
    padding: 5px;
  }
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    font-weight: 100;
  }

  h1 {
    color: firebrick;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  h2 {
    color: firebrick;
    text-transform: capitalize;
    font-size: 2.5em;
    font-weight: 50;
  }

  @media (min-width: 600px) {
    main {
      max-width: none;
    }
  }
</style>
