<script>
  let beltColour, name, age;

  function addStudentHandler() {
    console.log(`Adding ${name}, ${beltColour}`);
  }
</script>

<main>
  <form on:submit|preventDefault={addStudentHandler} on:click>
    <h2>Add Student</h2>
    <div>
      <input id="name" placeholder="Full Name" bind:value={name} type="text" />
      <input
        id="belt_colour"
        placeholder="belt colour"
        bind:value={beltColour}
        type="text" />
      <input id="age" placeholder="age" bind:value={age} type="number" />
      <button type="submit">Sign up</button>
    </div>
  </form>
</main>
