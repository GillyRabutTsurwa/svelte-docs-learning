<script>
  import CustomButton from "./components/CustomButton.svelte";
  let title = "DOM Event Forwarding";

  function clickMessage() {
    alert("Bouton Clicked");
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
    <p>Event forwarding can work on DOM events as well</p>
    <p>
      We want to get notified of clicks on our <code>CustomButton</code>. To do this, we just need to froward click events on the button element in CustomButton.svelte
    </p>
  </div>

  <CustomButton on:click={clickMessage} />
  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/dom-event-forwarding" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
