<script>
  export let name;
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name}!</h1>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
  <p>
    Pour cette première partie, j'écris pas de code. Néanmoins, voici ce qu'il
    est couvert
  </p>
  <ul>
    <li>Adding Data</li>
    <li>Dynamic Attributes</li>
    <li>Styling</li>
    <li>Nested Components</li>
    <li>HTML Tags</li>
    <li>Making an App (Optional to review)</li>
  </ul>
</main>
