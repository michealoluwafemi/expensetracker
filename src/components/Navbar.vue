<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <a class="navbar-brand" href="#">FMJ Expense</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item" v-for="(link, key) in links"  :key="key">
          <router-link
            :class="link.class"
            :to="link.to">{{ link.title }}
          </router-link>
        </li>
        <li class="nav-item">
          <router-link
            to="#myModal"
            class="nav-link"
            data-toggle="modal"
            data-target="#myModal"
            >Add Expense
          </router-link>
        </li>
        <!-- <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
            Dropdown
          </a>
          <div class="dropdown-menu" aria-labelledby="navbarDropdown">
            <a class="dropdown-item" href="#">Action</a>
            <a class="dropdown-item" href="#">Another action</a>
            <div class="dropdown-divider"></div>
            <a class="dropdown-item" href="#">Something else here</a>
          </div>
        </li> -->
      </ul>
      <ul class="mr-auto right">
        <li class="nav-link">Total Expense #{{ totalExpense }}</li>
      </ul>
    </div>
  </nav>
  <!-- <nav class="navbar navbar-expand-sm bg-light fixed-top">
    <ul class="navbar-nav">
      <li class="nav-item" v-for="(link, key) in links"  :key="key">
        <router-link
          :class="link.class"
          :to="link.to">{{ link.title }}
        </router-link>
      </li>
    </ul>
  </nav> -->
</div>
</template>

<script>
export default {
  name: 'navbar',
  props: ["totalExpense"],
  data () {
    return {
      links: [
        {
          to: "/",
          title: "Dashboard",
          class: "nav-link"
        },
        {
          to: "/view-all",
          title: "Expenses",
          class: "nav-link"
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</script>
