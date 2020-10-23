<script>
  let name = "Leo";
  let belt = "orange";
  let firstName = "Jimi";
  let lastName = "Hendrix";
  $: fullName = `${firstName} ${lastName}`;
  function changeColor() {
    belt = "black";
  }
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <h1>Hello {name}!</h1>
  <p style="color: {belt}">{fullName} - {belt} belt</p>
  <button on:click={changeColor}>Change color</button>
  <input bind:value={firstName} />
  <input bind:value={lastName} />
  <input bind:value={belt} />
</main>
