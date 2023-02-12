<template>
  <!-- NO ES NECESARIO TOCAR ESTE ARCHIVO -->
  <!-- <navbar /> -->

  <nav>
    <div class="inicio">
      <router-link to="/">INICIO</router-link> |
    </div>
    <div class="nav-links">
      <router-link to="/vista1">DATOS Y TABLAS</router-link> |
      <router-link to="/vista2">FICHA TECNICA</router-link> |
      <router-link to="/vista3">CONTACTO</router-link>
    </div>
  </nav>

  <router-view/>
</template>

<script>

  import Navbar from "./components/Navbar"

  export default {

   components: {
      Navbar
   }
    
  }


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #4AA873;
}
</style>