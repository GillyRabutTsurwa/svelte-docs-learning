<script>
  let title = "Promises With Await Blocks";

  async function fetchGoodBois() {
    try {
      const response = await fetch("https://dog.ceo/api/breeds/image/random");
      const data = await response.json();
      console.log(data);
      console.log(`Promise Status: ${data.status}`);
      return data;
    } catch (error) {
      console.log(error);
    }
  }

  let myPromise = fetchGoodBois();

  function handeClick() {
    // Still don't understand why we need this line as well as the same one above. Mais sans les deux, ça marche pas. J'ai testé. En tout cas, J'aime ce que j'ai appris.
    myPromise = fetchGoodBois();
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

  .promise-container {
    width: 300px;
    height: 300px;
  }

  img {
    width: 100%;
    height: 100%;
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
  <div class="docs-read" />

  <div class="code" />
  <button on:click={handeClick}>Click 4 Random Dog</button>

  <div class="promise-container">
    <!-- Alors que l'on est en train d'accueilir nos données, "Loading good bois", s'affiche. myPromise contient une fonctionne qui consume une promesse. -->
    {#await myPromise}
      <p>Loading good bois...</p>
      <!-- Après que nos données sont accueillies, on va rendre une image aléatoire d'un chien -->
    {:then promiseData}
      <img src={promiseData.message} alt="Dog" />
    {:catch error}
      <!-- Mais si une erreur s'est produite, on va afficher "There was an error" -->
      <strong>There was an error</strong>
    {/await}
  </div>

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/keyed-each-blocks" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
