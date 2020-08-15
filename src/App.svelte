<script>
  let title = "Looping with Each Blocks";

  let cats = [
    { id: "J---aiyznGQ", name: "Keyboard Cat" },
    { id: "z_AbfPXTKms", name: "Maru" },
    { id: "OUtn3pvWmpg", name: "Henri The Existential Cat" }
  ];
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
      If you need to loop over lists of data, use an
      <strong>each block</strong>
      . You can get the current index as a second argument, like so
    </p>
  </div>

  <div class="code">
    <ul>
      {#each cats as currentCat, index}
        <li>
          <a
            href="https://www.youtube.com/watch?v={currentCat.id}"
            target="_blank">
            {index + 1}: {currentCat.name}
          </a>
        </li>
      {/each}
    </ul>
  </div>

  <!-- small NOTE: not relevant to the topic. But interesting how we don't have to use string interpolation or template literals, or even binding for the href attribute above. We just our brackets as usual and our data, and it works. Maybe I'm missing something.. Either way, keep this in mind. -->

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/else-if-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
