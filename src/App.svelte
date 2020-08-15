<script>
  let title = "If Blocks";

  let user = {
    isLoggedIn: false
  };

  function toggle() {
    user.isLoggedIn = !user.isLoggedIn;
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
      Svelte has a really good way of rendering components conditionally. Pay
      attention to the syntaxe. Very different from VueJS v-if syntaxe and React
      JSX syntaxe.
    </p>
  </div>
  <div class="code">
    <!-- We wrap our comment in an if block -->
    {#if user.isLoggedIn}
      <button on:click={toggle}>Logged In</button>
    {/if}

    {#if !user.isLoggedIn}
      <button on:click={toggle}>Logged Out</button>
    {/if}
  </div>

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/if-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
