<script>
  import Main from "../components/Main.svelte";
  import SideBar from "../components/SideBar.svelte";
  import TimeLine from "../components/TimeLine.svelte";
  import Header from "../components/Header.svelte";
</script>

<style>
  :global(body) {
    background-color: white;
    color: black;
  }
</style>

<Header />
<Main>
  <TimeLine />
  <SideBar />
</Main>
