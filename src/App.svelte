<script>
  import Child from "./components/Child.svelte";
  let title = "Component Events";

  // here is the function that executes as a result of the parent (this App component) listening to the event by the child component. This function will take an event parametre (e), similar to vanilla Javascript, but not with the same properties.
  // this e object contains two properties worth mentioning:
  // e.type = the name of the event being passed (je sais pas lorsque l'on va l'utiliser)
  // e.detail = the data passed on from the child.
  function handleMessage(e) {
    console.log(e);
    const { type, detail } = e;
    console.log(type);
    console.log(detail);
    console.log(detail.text);
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

  .code {
    width: 100%;
    height: 80vh;
    border: 2.5px solid #ff3e00;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }

  /* Mais celui-ci marche bien */
  :global(.colour-change) {
    color: magenta;
  }
</style>

<main>
  <h1 id="title">{title}</h1>
  <div class="docs-read">
    As we've briefly seen already, you can listen to any event on an element
    with the on: directive:
  </div>

  <!-- NEW: on the declaration of the child component in the parent component is where we listen for our event from the child. also, we make a function to handle the event, and in which our data from the child (if there is any) can be accessed. L'idée est exactement pareil que celle de Vue, mais le syntaxe est un peu différent (mais pas trop) -->
  <Child on:message={handleMessage} />
  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/keyed-each-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
