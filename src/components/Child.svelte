<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  function ditGutenTag() {
    dispatch("message", {
      text: "Guten-Tag"
    });
  }
</script>

<button on:click={ditGutenTag}>Click 2 Salute</button>
