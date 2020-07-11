<script>
  let title = "Reactivity";
  let count = 0;
  //NEW:
  function handleClick() {
    count += 1;
  }
</script>

<style>
  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
    text-align: center;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  button {
    cursor: pointer;
  }
</style>

<main>
  <h1>{title}</h1>
  <div class="docs-read">
    At the heart of Svelte is a powerful system of reactivity for keeping the
    DOM in sync with your application state — for example, in response to an
    event.
  </div>
  <div class="code">
    <button on:click={handleClick}>Clicked {count} Times</button>
  </div>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
</main>
