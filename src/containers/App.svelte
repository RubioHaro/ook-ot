<script>
  import Main from "../components/Main.svelte";
  import SideBar from "../components/SideBar.svelte";
  import TimeLine from "../components/TimeLine.svelte";
  import Header from "../components/Header.svelte";
</script>

<style>
  @import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@100&display=swap");
  @import url("https://fonts.googleapis.com/css2?family=Rubik:wght@900&display=swap");

  :global(body) {
    background-color: #fafafa;
    color: black;
    font-family: "Montserrat", sans-serif;
    margin: 0;
    padding: 0;
  }

  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
    
  }
</style>

<Header />
<Main>
  <TimeLine />
  <SideBar />
</Main>
