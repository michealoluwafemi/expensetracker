<template>
  <div id="app">
    <div id="nav">
      <Navbar :total-expense="totalExp" />
      <!-- <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> -->
    </div>
    <div class="container">
      <AddExpense :expense="expenses" @save="updateExpense"/>
      <div class="allexpenses">
        <div class="exp-container">
          <div class="card" v-for="(expense, key) in expenses"  :key="key">
            <div class="card-body">
              <h4 class="card-title">{{ expense.title }}</h4>
              <p class="card-text">#{{ expense.amt }}</p>
              <button @click="viewExpense(key)" class="btn btn-primary" data-toggle="modal" data-target="#myExp">View</button>
            </div>
            <SingleExpense :single-expense="exp" />
          </div>
        </div>
      </div>

      <router-view/>
    </div>
  </div>
</template>

<script>
  import Navbar from '@/components/Navbar.vue'
  import AddExpense from '@/components/AddExpense.vue'
  import SingleExpense from '@/components/SingleExpense.vue'

  export default {
    name: 'app',
    components: {
      Navbar,
      AddExpense,
      SingleExpense
    },
    data () {
      return {
        totalExp: 0,
        expenses: [],
        exp: []
      }
    },
    methods: {
      // show: function () {
      //   alert("mfgjfjk");
      // },
      //
      updateExpense(item) {
        this.expenses.push(item);
        this.totalExp = parseFloat(this.totalExp) + parseFloat(item.amt);
        //alert(item.length);
      },
      viewExpense(i) {
        this.exp = {
          "title": this.expenses[i].title,
          "amt": this.expenses[i].amt,
          "date": this.expenses[i].date,
          "time": this.expenses[i].time,
          "flag": this.expenses[i].flag,
          "note": this.expenses[i].note
        }
        //alert(e.title+"\n"+e.amt);
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
