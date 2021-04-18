<script>
  let title = "Binding Text Inputs";
  let  name = "world";
  let jina = "";

  // NOTE: the vanilla javascript way
  function changeInputVanilla(e) {
    console.log(e);
    name = e.target.value;
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
    <p>
      As a general rule, data flow in Svelte is top down — a parent component can set props on a child component, and a component can set attributes on an element, but not the other way around.
    </p>
    <p>
      Sometimes it's useful to break that rule. Take the case of the input element in this component — we could add an on:input event handler that sets the value of name to event.target.value, but it's a bit... boilerplatey. It gets even worse with other form elements, as we'll see.
    </p>
    <p>
      Instead, we can use the bind:value directive:
    </p>
    <p>
      This means that not only will changes to the value of name update the input value, but changes to the input value will update name.
    </p>         
  </div>      

  <div class="my-inputs">
    <input type="text" on:input={changeInputVanilla}>
    <h3>Hello {name}</h3>
  
     <!-- NOTE: the svelte (javascript frameworks) way -->
    <input type="text" bind:value={jina}>
    <h3>Hello {jina}</h3> 
  </div>

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/text-inputs" target="_blank">
      Svelte tutorial
    </a> 
  </p>
</main> 
