<script>
  let title = "Reactivity";
  let count = 0;
  function handleClick() {
    count += 1;
  }
  //NEW:
  $: doubleCount = count * 2;
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
      When assigning reactive declarations, Svelte interprets the code to mean,
      <strong>
        "re-run this code whenever any of the referenced values change"
      </strong>
      . This is very similar to the computed property in Vue.
    </p>
    <p>
      Although reactive values are optional, because you can just change the
      values in the HTML markup, they become particularly valuable when you need
      to reference them multiple times, or you have values that depend on other
      reactive values.
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
