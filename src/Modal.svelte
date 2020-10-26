<script>
  let show = true;
  let promo = false;
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

  .promo {
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
    <div class="backdrop">
      <div class="modal" class:promo>
        <p>Sign up for offers</p>
      </div>
    </div>
  {/if}
</main>
