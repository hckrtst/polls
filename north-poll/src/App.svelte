<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./components/Tabs.svelte";
  import AddPollForm from "./components/AddPollForm.svelte";

  let tabs = ["Add Poll", "Active Polls"];
  let activeTab = tabs[0];

  function handleSelectTab(event) {
    activeTab = event.detail.tab;
  }

  let polls = [
    {
      ques: "what is the second largest country by landmass",
      ansA: "Australia",
      ansB: "Canada"
    },
  ];

  function handleAddPoll(e) {
    console.log(e.detail);
  }
</script>

<style>
  main {
    max-width: 960px;
    margin: 40px auto;
  }
</style>

<Header />
<main>
  <Tabs {tabs} {activeTab} on:selectTab={handleSelectTab} />
  {#if activeTab === tabs[0]}
    <AddPollForm on:addPoll={handleAddPoll}/>
  {:else}
    {#each polls as poll}
      <p>{poll.ques}</p>
    {/each}
  {/if}
</main>

<Footer />
