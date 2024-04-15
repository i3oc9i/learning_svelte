<script>
  import Card from "./lib/Card.svelte";
</script>

<main>
  <h1>Slots</h1>

  <Card>
    <div slot="header">
      <h2>Picsum</h2>
    </div>
    <div slot="body">
      <img src="https://picsum.photos/100/100" alt="Vite" />
    </div>
    <div slot="footer">
      <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
        labore et dolore magna aliqua.
      </p>
    </div>
  </Card>
  <Card>
    <div slot="header">
      <h2>Picsum</h2>
    </div>
    <div slot="body">
      <img src="https://picsum.photos/100/150" alt="Vite" />
    </div>
  </Card>
  <Card>
    <div slot="header">
      <h2>Vite</h2>
    </div>
    <div slot="body">
      <img src="./public/vite.svg" alt="Vite" />
    </div>
    <div slot="footer">
      <button>More Info</button>
    </div>
  </Card>
  <Card />
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

  @media (min-width: 600px) {
    main {
      max-width: none;
    }
  }
</style>
