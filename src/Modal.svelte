<script>
  let show = true;
  let promo = true;
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
  {#if show}
    <div class="backdrop" class:promo>
      <div class="modal">
        <p>Sign up for offers</p>
      </div>
    </div>
  {/if}
</main>
