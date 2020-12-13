<script>
  import Header from "./components/Header.svelte";
  import Footer from "./components/Footer.svelte";
  import Tabs from "./components/Tabs.svelte";
  import AddPollForm from "./components/AddPollForm.svelte";
  import PollList from "./components/PollList.svelte";

  let tabs = ["Add Poll", "Active Polls"];
  let activeTab = tabs[0];

  function handleSelectTab(event) {
    activeTab = event.detail.tab;
  }

  let polls = [
    {
      id: 1,
      ques: "what is the second largest country by landmass",
      ansA: "Australia",
      ansB: "Canada",
      voteA: 10,
      voteB: 4
    },
  ];

  function handleAddPoll(e) {
    const poll = {...e.detail, id: Math.random(), voteA: 0, voteB: 0};
    polls = [...polls, poll];
    activeTab = tabs[1];
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
    <PollList {polls} />
    
  {/if}
</main>

<Footer />
