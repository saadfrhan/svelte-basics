<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let buttons = [];
</script>

<div class="button-container">
  <button on:click={() => dispatch("clickHeaderToggler", true)}> Show </button>
  <button on:click={() => dispatch("clickHeaderToggler", false)}> Hide </button>
</div>

<div class="button-container">
  {#each buttons as button}
    <button on:click={() => dispatch("clickStory", button)}>
      {button.text}
    </button>
  {/each}
</div>

<style>
  .button-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    padding: 2em 1em;
  }
  button {
    font-family: "Nunito", sans-serif;
    display: block;
    font-size: 1.2rem;
    margin-inline: 10px;
    transition: 1s;
    padding: 0.7em 1em;
    cursor: pointer;
    border-radius: 50px;
    background-color: #40b3ff;
    color: white;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
      0 2px 4px -1px rgba(0, 0, 0, 0.06);
  }
</style>
