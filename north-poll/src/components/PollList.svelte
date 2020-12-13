<script>
  import Poll from './Poll.svelte';
  export let polls;
</script>

<style>
  .poll-list{
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
</style>

<div class="poll-list">
  {#each polls as poll (poll.id)}
    <div><Poll {poll} /></div>
  {/each}
</div>

