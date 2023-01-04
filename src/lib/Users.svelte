<script>
  import AddUser from "./AddUser.svelte";
  import UserCard from "./UserCard.svelte";
  console.log(localStorage.length);
  if (localStorage.length === 0) {
    localStorage.setItem("1", `[]`);
  }
  let getUserfromLS = localStorage.getItem("1");

  let usersDoc = JSON.parse(getUserfromLS);
  let demoData = {
    title: "Title of Card",
    Message:
      "Believe In YourSelf <br> To improve is to change, To be <strong> Perfect </strong>  is to change often. ",
  };

  let Vod;
  $: usersInfo = usersDoc;
  let removeElement = (value) => {
    usersDoc = usersDoc.filter((item, i) => i != value);
    Vod = JSON.stringify(usersDoc);
    localStorage.setItem("1", Vod);
  };
  let doneForm = (e) => {
    usersDoc = [
      { title: e.detail.title, message: e.detail.message },
      ...usersDoc,
    ];
    Vod = JSON.stringify(usersDoc);
    console.log(Vod);

    localStorage.setItem("1", Vod);
  };
</script>

<div>
  <div class="container">
    <AddUser on:doneForm={doneForm} />
    <div class="column_con">
      <h2>Demo Card :</h2>
      <UserCard title={demoData.title} message={demoData.Message} />
    </div>
  </div>
  <div class="container">
    {#each usersInfo as item, i}
      <UserCard {...item} on:remove={() => removeElement(i)} />
    {/each}
  </div>
</div>

<style>
  .container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  .column_con {
    display: flex;
    flex-direction: column;
  }
</style>
