<script>
  // NEW: importing and initialising the dispatcher
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();

  // NOTE: this function will be responsible for using the dispatcher to send the event up to the parent. this dispatcher takes 2 arguments: 1st one is the name of the event that will be sent for the parent to listen to (in our case, "message"), and the 2nd one is the data that we want to send up to the parent (the object with the text property).
  function ditGutenTag() {
    dispatch("message", {
      text: "Guten-Tag"
    });
  }
</script>

<button on:click={ditGutenTag}>Click 2 Salute</button>
