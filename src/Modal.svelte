<script>
  export let showModal = true;
  let promo = true;
  export let message = "Sale! Sale!";
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

  .promo .modal {
    padding: 10px;
    background-color: seagreen;
    border-radius: 5px;
    max-width: 1200px;
    margin: 10% auto; /* position in center */
    text-align: center;
  }
</style>

<main>
  {#if showModal}
    <div class="backdrop" class:promo>
      <div class="modal">
        <p>{message}</p>
      </div>
    </div>
  {/if}
</main>
