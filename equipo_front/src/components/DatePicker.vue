<template>
<!-- <div class="selector_fecha">
      <label id="selecor_option">Seleccione la fecha en que desea los Reportes</label><br>
      <h4>Start DATE</h4>
      <input type="datetime-local" id="start" min="2023-02-01">
      <h4>Stop DATE</h4>
      <input type="datetime-local" id="stop" value="2023-05-06">
      <button @click="report">Traer Reporte</button>
</div> -->
</template>

<script>
// ASÍ ES COMO RECIBIMOS LOS DATOS EN DE UN COMPONENTE parenthesizedExpression, EN ESTE CASO LA VISTA1
export default {
  name: 'TableHead',
  props: {
  },
  data() {
    return {
    };
  },
  methods: {
    reporte() {
        this.$emit('report')
    }
  },
}
</script>

<style>
</style>