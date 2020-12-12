<script>
  import { createEventDispatcher } from "svelte";
  import Child from "./Child.svelte";

  // this component is responsible for listening to the event from the child component and forwarding it to the parent component. But as the docs says, this is a lot of code and can get cumbersome (though I see it having its use cases). The shorter and preferred version is coming in the next branch
  const dispatch = createEventDispatcher();

  function forwardMessage(event) {
    // dispatch("message", event.detail); // this works, but I prefer celui dessous:
    dispatch(event.type, event.detail); // because event.type = name of event = message
  }
</script>

<Child on:message={forwardMessage} />
