<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./components/Tabs.svelte";

  let tabs = ["Add Poll", "Active Polls"];
  let activeTab = tabs[0];
</script>

<style>
  main {
    max-width: 960px;
    margin: 40px auto;
  }
</style>

<Header />
<main>
  <Tabs {tabs} {activeTab} />
</main>

<Footer />
