<script>
  let title = "DOM Events";
  let coordinates = {
    x1: 0,
    x2: 0,
    y1: 0,
    y2: 0
  };

  // THIS DOES NOT WORK. No access to the document tree for some reason here. but inside the javascript function it works well
  let pageText = document.querySelectorAll(".texto");

  // we have access to the event object in svelte
  function handleMouseMove(e) {
    coordinates.x1 = e.clientX;
    coordinates.y1 = e.clientY;

    coordinates.x2 = e.screenX;
    coordinates.y2 = e.screenY;
  }

  function accessEventObject(e) {
    console.log(e);
  }

  function toggleColour() {
    let pageText = document.querySelectorAll(".texto");
    pageText.forEach(currentText => {
      console.log(currentText);
      console.dir(currentText);
      currentText.classList.toggle("colour-change");
    });
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
  <h1>{title}</h1>
  <div class="docs-read">
    As we've briefly seen already, you can listen to any event on an element
    with the on: directive:
  </div>

  <div on:mousemove={handleMouseMove} class="code">
    <p class="texto">
      The mouse position (client) is {coordinates.x1} x {coordinates.y1}
    </p>
    <p class="texto">
      The mouse position (screen) is {coordinates.x2} x {coordinates.y2}
    </p>
  </div>

  <button on:click={accessEventObject} class="btn">Event Object Info</button>
  <button on:click={toggleColour} class="btn">Toggle Colour</button>

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/keyed-each-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
