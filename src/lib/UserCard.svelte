<script>
  import { createEventDispatcher } from "svelte";

  export let title, message;
  let dispatch = createEventDispatcher();
  let handleRemove = () => {
    dispatch("remove")
  };
</script>

<div class="card">
  <h1 class="title">{title}</h1>
  <p>{@html message}</p>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <img
    on:click={handleRemove}
    src="https://cdn-icons-png.flaticon.com/512/9309/9309009.png"
    alt="remove"
    width="24"
  />
</div>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
  .card {
    position: relative;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    width: fit-content;
    border: 1px solid black;
    padding: 15px 25px;
    margin: 10px;
    border-radius: 10px;
    transition: all 0.3s ease;
    height: fit-content;
  }
  .title {
    font-family: "Lato", sans-serif;
    margin-bottom: 7px;
    text-align: center;
  }
  p {
    font-family: "Poppins", sans-serif;
    font-weight: 500;
    font-size: 1.2rem;
    color: #2e2e2e;
  }
  img {
    position: absolute;
    right: 5px;
    top: 5px;
    transition: all 0.3s ease;
    opacity: 0.7;
  }
  img:hover {
    transition: all 0.3s ease;
    opacity: 1;
  }
</style>
