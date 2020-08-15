<script>
  import Thing from "./components/Thing.svelte";

  let things = [
    { id: 1, colour: "#0d0887" },
    { id: 2, colour: "#6a00a8" },
    { id: 3, colour: "#b12a90" },
    { id: 4, colour: "#e16462" },
    { id: 5, colour: "#fca636" }
  ];

  function handleClick() {
    things = things.slice(1);
  }

  let title = "Keyed Each Blocks";

  //TESTING:
  $: console.log(things);
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
      Just like in Vue and React, it is recommended to insert a unique key into
      our iterations. Not doing so won't break the app, but could lead to
      unexpected behaviours. Especially when manipulating data.
    </p>
    <p>
      <strong>
        We make a key by putting the value of the key in parantheses in our each
        block.
      </strong>
    </p>
  </div>

  <div class="code">
    <button on:click={handleClick}>Remove first thing</button>
    {#each things as currentThing (currentThing.id)}
      <Thing current={currentThing.colour} />
    {/each}
  </div>

  <!-- Try removing them by removing the key declaraion. The behaviour is bizzare. Je peux pas l'expliquer. -->

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/keyed-each-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
