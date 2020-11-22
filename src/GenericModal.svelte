<script>
  export let showModal = true;
</script>

<style>
  .backdrop {
    width: 100%;
    height: 100%;
    position: fixed;
    background: rgba(0, 0, 0, 0.7);
  }
  .modal {
    padding: 10px;
    background-color: chocolate;
    border-radius: 5px;
    max-width: 1200px;
    margin: 10% auto; /* position in center */
    text-align: center;
  }
</style>

<main>
  {#if showModal}
    <div class="backdrop" on:click|self>
      <div class="modal">
        <slot />
      </div>
    </div>
  {/if}
</main>
