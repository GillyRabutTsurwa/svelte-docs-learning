<script>
  let title = "Binding"
  let num1 = 1;
  let num2 = 2;

  $: sum = num1 + num2;

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
      In the DOM, everything is a string. That's unhelpful when you're dealing with numeric inputs — type="number" and type="range" — as it means you have to remember to coerce input.value before using it.
    </p>
    <p>
      With bind:value, Svelte takes care of it for you:
    </p>       
  </div>      

  <div class="my-inputs">
    <label>
      <input type="number" bind:value={num1} min=0 max=20>
      <input type="range" bind:value={num1} min=0 max=20>
    </label>
    <label>
      <input type="number" bind:value={num2} min=0 max=20>
      <input type="range" bind:value={num2} min=0 max=20>
    </label>
  </div>

  <p> {num1} + {num2} = {sum} </p>

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/text-inputs" target="_blank">
      Svelte tutorial
    </a> 
  </p>
</main> 
