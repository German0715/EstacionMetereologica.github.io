<template>
  <!-- NO ES NECESARIO TOCAR ESTE ARCHIVO -->
  <div class="inicio">
      <button><router-link to="/">Inicio</router-link></button>
    <div class="nav-links">
        <button><router-link to="/vista1">Datos</router-link></button>
        <button><router-link to="/vista2">Ficha Técnica</router-link> </button>
        <button><router-link to="/vista3">Nosotros</router-link></button>
      </div>
    </div>
  <router-view/>
</template>

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
button {
 --color: #244053;
 font-family: Helvetica;
 display: inline-block;
 width: 8em;
 height: 2.6em;
 line-height: 2.5em;
 margin: 5px;
 position: relative;
 overflow: hidden;
 border: 2px solid var(--color);
 -webkit-transition: color .5s;
 transition: color .5s;
 z-index: 1;
 font-size: 17px;
 border-radius: 6px;
 font-weight: 500;
 color: var(--color);
}

button:before {
 content: "";
 position: absolute;
 z-index: -1;
 background: var(--color);
 height: 150px;
 width: 200px;
 border-radius: 50%;
}

button:hover {
 color: #fff;
}

button:before {
 top: 100%;
 left: 100%;
 -webkit-transition: all .7s;
 transition: all .7s;
}

button:hover:before {
 top: -30px;
 left: -30px;
}

button:active:before {
 background: #3a0ca3;
 -webkit-transition: background 0s;
 transition: background 0s;
}


.nav-links{
  display: flex;
  justify-content: right;
  margin-left:900px ;
}

.inicio{
  display: flex;
  justify-content: left;
}
</style>