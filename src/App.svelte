<script>
  let title = "Binding";
  let subtitle = "Group Inputs";

let scoops = 1;
// juss like Vue (je crois), this array is the current selected checkbox of all the values in the array below
let checkedFlavoursArr = [];

let flavoursMenu = ["Cookies & Cream", "Mini Chocolate Chip", "Raspberry Ripple"];

function join(flavoursArr) {
  if (flavoursArr.length === 1) return flavoursArr[0];
  return `${flavoursArr.slice(0,-1).join(", ")} and ${flavoursArr[flavoursArr.length - 1]}`;
}

$: {
  console.log(checkedFlavoursArr); 
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

    <label>
      <input type="radio" bind:group={scoops} value={1}>
      One Scoop
    </label>
    <label>
      <input type="radio" bind:group={scoops} value={2}>
      Two Scoops
    </label>
    <label>
      <input type="radio" bind:group={scoops} value={3}>
      Three Scoops
    </label>  

    <p>and just like vue, we can loop through inputs elements to create them more dynamically and efficently</p>

    {#each flavoursMenu as currentFlavour}
      <label>
        <input type="checkbox" bind:group={checkedFlavoursArr} value={currentFlavour}>
        {currentFlavour}
      </label>
    {/each}

    {#if checkedFlavoursArr.length === 0}
      <p>Please Select at least one flavour</p>
    {:else if  checkedFlavoursArr.length > scoops}
       <p>Can't order more flavours than scoops</p>
    {:else}
      <h6>You have {scoops} {scoops === 1 ? "scoop" : "scoops"} of {join(checkedFlavoursArr)}</h6>
    {/if} 


   


  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/checkbox-inputs" target="_blank">
      Svelte tutorial
    </a> 
  </p>
</main> 
