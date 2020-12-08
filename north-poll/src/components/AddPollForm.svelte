<script>
  import Button from "./Button.svelte";
  import { createEventDispatcher } from 'svelte';

  let fields = {
    ques: '',
    ansA: '',
    ansB: ''
  };
  let errors= {
    ques : '',
    ansA : '',
    ansB : ''
  };
  let valid = false;

  function validateInput(field, len) {
    if (field.trim().length < len) {
      return [false, `Invalid  input, length should be at least ${len}`];
    }
    return [true, ''];
  }

  const dispatch = createEventDispatcher();

  function handleAdd() {
    valid = true;
    let ok = false;
    [ok, errors.ques] = validateInput(fields.ques, 5);
    if (!ok) valid = false;
    else errors.ques = '';
    [ok, errors.ansA] = validateInput(fields.ansA, 2);
    if (!ok) valid = false;
    else errors.ansA = '';
    [ok, errors.ansB] = validateInput(fields.ansB, 2);
    if (!ok) valid = false;
    else errors.ansB = '';

    if (valid) {
      dispatch('addPoll', fields);
    }
  }
</script>
<form on:submit|preventDefault={handleAdd}>
  <div class="form-field">
    <label for="question">Question:</label>
    <input type="text" id="question" bind:value={fields.ques}>
    <div class:errmsg={errors.ques.length > 1}>{errors.ques}</div>
  </div>
  <div class="form-field">
    <label for="answer-a">Answer A:</label>
    <input type="text" id="answer-a" bind:value={fields.ansA}>
    <div class:errmsg={errors.ansA.length > 1}>{errors.ansA}</div>
  </div>
  <div class="form-field">
    <label for="answer-b">Answer B:</label>
    <input type="text" id="answer-b" bind:value={fields.ansB}>
    <div class:errmsg={errors.ansB.length > 1}>{errors.ansB}</div>
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
  .errmsg{
    color: red;
  }
  
</style>