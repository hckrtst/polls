<script>
  import { each } from "svelte/internal";
  import Modal from "./Modal.svelte";

  let name = "Leo";
  let belt = "orange";
  let firstName = "Jimi";
  let lastName = "Hendrix";
  $: fullName = `${firstName} ${lastName}`;
  function changeColor() {
    belt = "black";
  }
  function removeStudent(id) {
    people = people.filter((person) => person.id != id);
  }

  let people = [
    { name: "yoshi", belt: "black", id: 1 },
    { name: "gawdy", belt: "brown", id: 2 },
    { name: "dandy", belt: "yellow", id: 3 },
  ];
</script>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
    color: chocolate;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
    color: indigo;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<Modal />
<main>
  <h1>Hello {name}!</h1>
  <p style="color: {belt}">{fullName} - {belt} belt</p>
  <button on:click={changeColor}>Change color</button>
  <input bind:value={firstName} />
  <input bind:value={lastName} />
  <input bind:value={belt} />
  <h2>Students</h2>
  <div>
    {#each people as person (person.id)}
      <p>{person.name}, {person.belt}</p>
      <button on:click={() => removeStudent(person.id)}>Remove</button>
    {:else}
      <p>No students yet</p>
    {/each}
  </div>
  {#if people.length === 0}
    <p>Time to sign up some students</p>
  {:else}
    <p>Busy schedule</p>
  {/if}
  <p />
</main>
