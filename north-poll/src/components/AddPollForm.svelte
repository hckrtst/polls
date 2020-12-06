<script>
  import Button from "./Button.svelte";
  let fields = {
    ques: '',
    ans_a: '',
    ans_b: ''
  };
  function handleAdd() {
    console.log(fields);
  }
</script>
<form on:submit|preventDefault={handleAdd}>
  <div class="form-field">
    <label for="question">Question:</label>
    <input type="text" id="question" bind:value={fields.ques}>
  </div>
  <div class="form-field">
    <label for="answer-a">Answer A:</label>
    <input type="text" id="answer-a">
  </div>
  <div class="form-field">
    <label for="answer-b">Answer B:</label>
    <input type="text" id="answer-b">
  </div>
  <Button>Add</Button>
</form>

<style>
  form{
    width: 400px;
    margin: 0 auto;
    text-align: center;
  }
  .form-field{
    margin: 18px auto;

  }
  input{
    width: 100%;
    border-radius:  6px;
  }
  label{
    margin: 10px auto;
    text-align: left;
  }
  
</style>