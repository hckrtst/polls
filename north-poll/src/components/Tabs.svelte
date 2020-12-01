<script>
  export let tabs = [];
  export let activeTab;
</script>

<style>
  .active {
    color: #312102;
    border-bottom: 2px solid;
    padding-bottom: 10px;
  }
  ul {
    color: #aaaaff;
    display: flex;
    justify-content: center;
    list-style-type: none;
    padding: 0;
  }
  li {
    margin: 0 16px;
    font-size: 25px;
    cursor: pointer;
  }
  .tabs {
    margin-bottom: 40px;
  }
</style>

<div class="tabs">
  <ul>
    {#each tabs as tab}
      <li
        class:active={tab === activeTab}
        on:click={() => {
          console.log(`${tab}`);
        }}>
        {tab}
      </li>
    {/each}
  </ul>
</div>
