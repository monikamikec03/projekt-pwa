<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top">
    <div class="container">
      <img class="card-header-pills" src="../assets/logo.png" style="width:4%">
      <a class="navbar-brand">
        <router-link to="/">DVD Haganj</router-link>
      </a>
      <button
        class="navbar-toggler toggler-example"
        type="button"
        data-toggle="collapse"
        data-target="#navbarResponsive"
        aria-controls="navbarResponsive"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon" @click="toggleNav"></span>
      </button>
      <div :class="{ 'show': showNav }" class="collapse navbar-collapse" id="navbarResponsive">
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a class="nav-link" id="c1">
              <router-link to="aktivnosti">Aktivnosti</router-link>
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link">
              <router-link to="natjecanja">Natjecanja</router-link>
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link">
              <router-link to="kontakt">Kontakt</router-link>
            </a>
          </li>
          <li v-if="!authenticated" class="nav-item" id="login">
            <a class="nav-link">
              <router-link to="login">Login</router-link>
            </a>
          </li>
          <li v-else class="nav-item hide" id="clanovi">
            <a class="nav-link">
              <router-link to="secure">Članovi</router-link>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  props: ["authenticated"],
  data() {
    return {
      showNav: false
    };
  },
  methods: {
    toggleNav() {
      this.showNav = !this.showNav;
    }
  }
};
</script>

<style scoped>
.black {
  color: black;
  font-size: 20pt;
  padding-top: 20px;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
}
.black:hover {
  color: orange;
}
.green {
  color: green;
}
</style>
