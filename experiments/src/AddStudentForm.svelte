<script>
  import { createEventDispatcher } from "svelte";
  let beltColour;
  let name, age;
  let skills = [];
  let dispatch = createEventDispatcher();

  function addStudentHandler() {
    dispatch("student", { name, age, beltColour, skills });
  }
</script>

<main>
  <form on:submit|preventDefault={addStudentHandler} on:click>
    <h2>Add Student</h2>
    <div>
      <input id="name" placeholder="Full Name" bind:value={name} type="text" />
      <select name="beltcolour" id="belt_colour" bind:value={beltColour}>
        <option value="red">red</option>
        <option value="yellow">yellow</option>
        <option value="black">black</option>
      </select>
      <input
        type="checkbox"
        bind:group={skills}
        value="sparring" />Sparring<br />
      <input
        type="checkbox"
        bind:group={skills}
        value="sommersault" />Sommersault<br />
      <input id="age" placeholder="age" bind:value={age} type="number" />
      <button type="submit">Sign up</button>
    </div>
  </form>
</main>
