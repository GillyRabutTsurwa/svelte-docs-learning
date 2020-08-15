<script>
  import Info from "./components/Info.svelte";

  let title = "Props";

  const pkg = {
    name: "Svelte",
    version: 3,
    speed: "blazing",
    website: "https://svelte.dev"
  };
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
      If you have an object of properties, you can 'spread' them on to a
      component instead of specifying each one:
    </p>
  </div>
  <div class="code">
    <!-- This first rendered child component is WITHOUT using spread -->
    <Info
      name={pkg.name}
      version={pkg.version}
      speed={pkg.speed}
      website={pkg.website} />
    <!-- NEW: This first rendered child component is WITH using spread -->
    <!-- I think I understand -->
    <!-- Under the hood, when we declare a props using an object. The name of the prop taken in by the child MUST be the same name of the property of the object (Look at object up at line 6). Svelte then recognises this. -->
    <!-- Still don't understand fully but for now, ça suffit. -->
    <Info {...pkg} />
  </div>

  <p>
    S'il te faut refraîchir la tête au sujet, consulter ce lien:
    <a href="https://svelte.dev/tutorial/spread-props" target="_blank">
      Svelte tutorial
    </a>
  </p>
</main>
