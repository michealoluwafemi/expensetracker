<template>
  <div id="app">
    <div id="nav">
      <Navbar :total-expense="totalExp" />
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    </div>
    <div class="container">
      <AddExpense :expense="expenses" @save="updateExpense"/>
      <router-view/>
    </div>
  </div>
</template>

<script>
  import Navbar from '@/components/Navbar.vue'
  import AddExpense from '@/components/AddExpense.vue'

  export default {
    name: 'app',
    components: {
      Navbar,
      AddExpense
    },
    data () {
      return {
        totalExp: 0,
        expenses: []
      }
    },
    methods: {
      show: function () {
        alert("mfgjfjk");
      },
      updateExpense(item) {
        this.expenses.push(item);
        this.totalExp = parseFloat(this.totalExp) + parseFloat(item.amt);
        alert(item.length);
      }
    }
  }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
#nav li{
  margin-left: 5px;
  margin-right: 5px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding-left: 15px;
  padding-right: 15px;
}

#nav a.router-link-exact-active {
  background: #42b983 !important;
  color: #FFF !important;
  border-radius: 5px;
}
</style>
