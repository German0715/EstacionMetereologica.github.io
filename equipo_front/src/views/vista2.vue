<template>
    <!-- ENCARGADOS VISTA 1:SOFIA, ERIKA, ALEXANDRA   -->

  <div class="about">
    <HelloWorld msg="FICHA TECNICA"/>
  </div>

  

</template>

<script>
import HelloWorld from '@/components/HelloWorld.vue';
import TableHead from '@/components/TableHead.vue';


export default {
  name: 'Vista2',
  //ACÁ SE AGREGAN LAS COMPONENTES QUE VAMOS A UTILIZAR
  components: {
    HelloWorld,
    TableHead,
  },
}
</script>

<style>
.historical {
  table-layout: fixed;
  width: 100%;
  border-collapse: collapse;
  border: 3px solid greenyellow;
}
</style>