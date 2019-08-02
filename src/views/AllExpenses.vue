<template>
  <div class="allexpenses">
    <div class="exp-container">
      <div class="card" v-for="(expense, key) in expense"  :key="key">
        <div class="card-body">
          <h4 class="card-title">h3</h4>
          <p class="card-text">{{ expense.amt }}</p>
          <a href="#" class="btn btn-primary">View</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'allexpenses',
  props: ["expense"],
  components: {

  }
}
</script>
<style scoped>
  .expenses {
    overflow: auto;
  }
  .exp-container {
    padding: 3em 5em;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-gap: 20px;
    overflow: auto;
  }
  .single-expense {
    text-align: center;
  }
</style>
