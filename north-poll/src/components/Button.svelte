<script>
  export let type='primary';
  export let flat = false;
  export let inverse = false;
</script>

<button class={type} class:flat={flat} class:inverse={inverse}>
  <slot></slot>
</button>

<style>
  button{
    border: 0;
    cursor: pointer;
    box-shadow: 1px 2px 3px rgba(0,0,0,0.2);
  }

</style>