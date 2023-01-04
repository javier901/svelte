<script>
  import { createEventDispatcher } from "svelte";

  let userddd = {};
  let dispatch = createEventDispatcher();
  let doneForm = () => {
    dispatch("doneForm", userddd);
    userddd.title = "";
    userddd.message = "";
  };
</script>

<form on:submit|preventDefault={doneForm}>
  <div class="text">
    <label for="titleInfo">Title : </label>
    <input
      type="text"
      name="titleInfo"
      id="titleInfo"
      bind:value={userddd.title}
      required
    />
  </div>
  <div>
    <label for="messageInfo">Message : </label>
    <textarea
      name="messageInfo"
      id="messageInfo"
      cols="25"
      rows="7"
      bind:value={userddd.message}
      required
    />
  </div>
  <div class="end">
    <button type="submit">Sumbit</button>
  </div>
</form>

<style>
  form {
    border: 1px solid #1a1a1ae3;
    width: fit-content;
    padding: 10px 20px;
    border-radius: 10px;
    margin: 10px;
  }
  div {
    display: flex;
    flex-direction: column;
    margin-bottom: 10px;
  }
  label {
    margin-left: 2px;
    font-size: 1.4rem;
    font-family: "Poppins", sans-serif;
  }
  input,
  textarea {
    padding: 5px;
    border: 2px solid #1c5af8;
    border-radius: 4px;
    font-size: 1.1rem;
    font-family: sans-serif;
  }
  .end {
    display: flex;
    align-items: center;
    margin: 0;
  }
  button {
    padding: 7px;
    background-color: transparent;
    border: 1px solid black;
    border-radius: 4px;
    font-size: 1.09rem;
    transition: all 0.3s ease;
    color: #053bc4;
  }
  button:hover {
    transition: all 0.2s ease;
    box-shadow: 3px 3px #131313;
  }
</style>
