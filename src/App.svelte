<script>
  import Users from "./lib/Users.svelte";
</script>

<main>
  <h1>Simple Notes App</h1>
  <Users />
</main>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Lato:wght@900&display=swap");
  h1 {
    text-align: center;
    margin-top: 10px;
    font-size: 2.5rem;
    font-family: "Lato", sans-serif;
    font-weight: 900;
    margin-bottom: 10px;
  }
  @media only screen and (min-device-width: 320px) and (max-device-width: 480px) {
      h1{
        font-size: 2rem;
      }
    }
</style>
