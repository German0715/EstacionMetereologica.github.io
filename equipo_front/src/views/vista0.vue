<template>
    <div class="header1">
      <div class="info">
      <h4>UNIVERSIDAD INDUSTRIAL DE SANTANDER</h4>
        <h1>ESTACIONES METEREOLÓGICAS - E3T UIS</h1>
      </div>
    </div>
    <div class="body1">
    </div>
</template>

<script>
import Footer from '@/components/Footer.vue';


export default {
    name: 'vista0',
    components: {
        Footer,
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Josefin+Sans:400,400i,600,600i');
html,body{
  margin:0;
  height:120%;
  font-family: 'Josefin Sans', sans-serif;

}

.header1{
  position:relative;
  overflow:hidden;
  display:flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: flex-start;
  align-content: flex-start;
  height:50vw;
  min-height:400px;
  max-height:550px;
  min-width:300px;
  color: #03242d;
}
.body1{
  content:"";
  width:100%;
  height:200%;
  position:absolute;
  top:0;
  left:0;
    -webkit-backface-visibility: hidden;
    -webkit-transform: translateZ(0); backface-visibility: hidden,
   scale(1.0, 1.0);
    transform: translateZ(0);
  background:#1B2030 url(https://images.unsplash.com/photo-1571993142257-eae0b44cf0f1?ixlib=rb-1.2.1&q=85&fm=jpg&crop=entropy&cs=srgb&ixid=eyJhcHBfaWQiOjE0NTg5fQ) 50% 0 no-repeat;
  background-size:100%;
  background-attachment:scroll;
  animation: grow 360s  linear 10ms infinite;
  transition:all 0.4s ease-in-out;
  z-index:-2
}
</style>
  
