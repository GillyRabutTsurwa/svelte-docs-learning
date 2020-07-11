<script>
  // NEW:
  import Nested from "./components/Nested.svelte";

  let title = "Props";
  let numRando = 0;

  function generateRandomNumber() {
    numRando = Math.floor(Math.random() * 200);
  }
</script>

<style>
  main {
    width: 1000px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: bold;
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
    <p>
      So far, we've dealt exclusively with internal state — that is to say, the
      values are only accessible within a given component. In any real
      application, you'll need to pass data from one component down to its
      children. To do that, we need to declare properties, generally shortened
      to 'props'. In Svelte, we do that with the export keyword. Edit the
      Nested.svelte component:
    </p>
  </div>
  <div class="code">
    <button on:click={generateRandomNumber}>Randomise Answer</button>
    <Nested answer={numRando} />
  </div>
  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/declaring-props" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
