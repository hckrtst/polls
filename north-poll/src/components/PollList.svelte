<script>
  export let polls;
</script>

<style>
  .poll-list{
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
</style>

<div class="poll-list">
  {#each polls as poll}
    <div>{poll.ques}</div>
  {/each}
</div>

