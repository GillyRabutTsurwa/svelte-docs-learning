<script>
  let title = "Binding";
  let subtitle = "Checkboxes";

  let oui = false; // variable responsible for changing the state of the checkbox
  let isChecked = false;
  let isCheckedTwo = false;

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

  .square {
    width: 20em;
    height: 20em;
    background-color: magenta;
    border: 5px solid transparent;
  }

  .stylesActivated {
    background-color: goldenrod;
    border: 5px solid slateblue;
  }
</style>

<main>
  <h1 id="title">{title}</h1>
  <h2>{subtitle}</h2>
  <div class="docs-read">
    <p>
      Checkboxes are used for toggling between states. Instead of binding to <code>input.value</code>, we bind it to <code>input.checked</code>
    </p>
    <p> 
      With bind:value, Svelte takes care of it for you:
    </p>   

    <div class="input-one">
      <label>
        <input type="checkbox" bind:checked={oui} >
      </label>
    </div>
    
    <!-- render this if oui = true (ie) if he checkbox is checked -->
    {#if oui}
      <p>Merci. On va remplir ta boîte de reception et vendre tes données personelles</p>
    {:else}
      <p>You must opt in to continue. Si vous payez pas, la produit, c'est vous</p> 
    {/if}

    <button disabled={!oui}>
      S'abonner
    </button>

    <div class="input-two">
      <label for="badInputName">
        <input type="checkbox" id="badInputName" bind:checked={isChecked}>
        {#if isChecked}
          <span>Bossman</span>
        {:else}
           <span>BigBoi</span>
        {/if}
      </label>
    </div>

    <div class="input-three">
      <input type="checkbox" bind:checked={isCheckedTwo}>
      <!-- we haven't learnt the class directive yet. Ça viens plus tard -->
      <div class="square" class:stylesActivated={isCheckedTwo}></div>
    </div>
  </div>      


  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/checkbox-inputs" target="_blank">
      Svelte tutorial
    </a> 
  </p>
</main> 
