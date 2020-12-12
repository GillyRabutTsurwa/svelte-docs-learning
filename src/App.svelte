<script>
  let title = "Event Modifiers";
  let name;

  function returnInputValue() {
    const myInput = document.getElementById("msgInput");
    if (myInput.value !== "") console.log(myInput.value);
  }

  function alertOnce() {
    alert("Je vais plus m'afficher. Seule cette fois-ci");
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

  /* TODO: Fait recherche à la raison que celui-ci marche pas: */
  /* .colour-change {
    color: magenta;
  } */

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

  <form id="myForm" on:submit|preventDefault={returnInputValue}>
    <input
      type="text"
      name="message"
      id="msgInput"
      placeholder="Type a message" />
    <input type="submit" value="Submit" />
  </form>
  <span>{name}</span>

  <button on:click|once={alertOnce} class="btn">Click Me</button>
  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/keyed-each-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
