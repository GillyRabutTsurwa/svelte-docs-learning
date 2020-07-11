<script>
  let title = "Reactivity";
  let titre = "Réactivité";
  let numbers = [1, 2, 3, 4, 5];
  //NEW:
  function addNumber() {
    numbers = [...numbers, numbers.length + 1];
  }
  $: console.log(numbers);
  $: sum = numbers.reduce((acc, currentNum) => acc + currentNum, 0);
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
    <div class="code">
      <button on:click={addNumber}>Add Number</button>
      <p>{numbers.join(' + ')} = {sum}</p>
    </div>
    <p>
      S'il te faut refraîchir la tête au sujet, consulter ce lien:
      <a
        href="https://svelte.dev/tutorial/updating-arrays-and-objects"
        target="_blank">
        Svelte tutorial
      </a>
    </p>
  </div>
</main>
