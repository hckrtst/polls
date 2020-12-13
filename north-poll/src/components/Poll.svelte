<script>
  export let poll;
</script>

<style></style>

<div class="poll">
  <h2>{poll.ques}</h2>
  <div class="answer">
    <div class="percent percent-a"></div>
    <span>{poll.ansA} ({poll.voteA}%)</span>
  </div>
  <div class="answer">
    <div class="percent percent-b"></div>
    <span>{poll.ansB} ({poll.voteB}%)</span>
  </div>
</div>