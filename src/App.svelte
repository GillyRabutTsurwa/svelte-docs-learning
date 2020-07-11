<script>
  let title = "Reactivity";
  let titre = "Réactivité";
  let count = 0;
  function handleClick() {
    count += 1;
  }
  $: doubleCount = count * 2;
  //NEW:
  $: console.log(`The count is ${count}`);
  //NEW:
  $: {
    console.log(`La valeur actuelle de count est ${count}`);
    console.log(`J'aime le Svelte. J'apprends la ${titre}`);
  }
  //NEW:
  $: {
    if (count > 10) {
      console.log("Woah. Coo down the pace");
    }
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
      Svelte automatically updates the DOM when your component's state changes.
      Often, some parts of a component's state need to be computed from other
      parts (such as a fullname derived from a firstname and a lastname), and
      recomputed whenever they change. For these, we have reactive declarations.
    </p>
    <p>
      We're not limited to declaring reactive values — we can also run arbitrary
      statements reactively. For example, we can log the value of count (the
      variable we have been working with till now) whenever it changes:
    </p>
    <p>Additionally, we can easily group statements together with a block</p>
    <p>We can also use $: to make if statements (for example) reactive.</p>
    <p>
      $: is very powerful. Et en apprenant de cette symbol je me trouve
      d'apprécier de plus en plus le property "computed" en Vue
    </p>
  </div>
  <div class="code">
    <button on:click={handleClick}>
      Clicked {count} {count === 1 ? 'Time' : 'Times'}
    </button>
    <p>{count} doubled is {doubleCount}</p>
  </div>
  <p>
    Visit the
    <a href="https://svelte.dev/tutorial">Svelte tutorial</a>
    to learn how to build Svelte apps.
  </p>
</main>
