<script>
  let title = "If Blocks";

  let x = 7;

  const increment = () => x++;
  const decrement = () => x--;
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
      For mote than two statements, we use
      <strong>else-if blocks</strong>
      . This is also much better than nesting if-statements.
    </p>
  </div>
  <div class="code">
    <!-- If we have more than two statements, we can chain those with else-if blocks. All this is just like regular Javascript. Just different syntaxe -->
    <button on:click={increment}>Increment</button>
    <button on:click={decrement}>Decrement</button>
    {#if x > 10}
      <p>{x} is greater than 10</p>
    {:else if x < 5}
      <p>{x} is less than 5</p>
    {:else}
      <p>{x} is between 5 and 10</p>
    {/if}
  </div>

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/else-if-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
