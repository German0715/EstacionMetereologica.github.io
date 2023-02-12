<template>

  <!-- ENCARGADOS VISTA 1:GERMAN, ALEXANDRA, ALEJANDRO   -->

  <!-- EN EL TEMPLATE SE AGREGA TODO EL CÓDIGO HTML CONTENIDO EN LAS ETIQUETAS <body></body> DE LA RESPECTIVA VISTA -->

  <div class="home">
    <!-- ASÍ SE AGREGA EL CONTENIDO ESTÁTICO QUE ESTÁ EN EL ASSETS, LOGOS, IMÁGENES... ETC -->
    <img alt="Vue logo" src="../assets/estacion_ejemplo.jpg">

    <!-- ASÍ SE AGREGA UN COMPONENTE, EL msg ES LA INFORMACIÓN QUE LE ENVIAMOS AL COMPONENTE -->
    <HelloWorld msg="ULTIMOS DATOS Y TABLAS"/> 
  </div>
  <div class="table-responsive" >
    <table class="table table-primary">

      <!-- ASÍ SE AGREGA UN COMPONENTE, EL msg ES LA INFORMACIÓN QUE LE ENVIAMOS AL COMPONENTE -->
      <TableHead :msgs="Header_table"/>
      <!-- NO SE PEOCUPEN POR AGREGAR COMPONENTES POR AHORA HAGAN EL HTML (ACÁ EN EL TEMPLATE) 
      Y EL CSS (ABAJO EN EL STYLE) COMO EN ESTE EJEMPLO Y LUEGO SE ORGANIZA POCO A POCO EN COMPONENTES CON EL JAVASCRIPT -->

      <tbody>
      <!-- EL v-for NOS SIRVE PARA IMPRIMIR DE FORMA REACTIVA Y DINAMÍCA LOS DATOS QEU TENGAMOS, SERVIRÁ PARA QUE LAS TABLAS SEAN DINÁMICAS -->
        <tr v-for="(station, index) in STATIONS" :key="station.index">
            <td> {{ station.name }} </td>
            <td> {{ station.last_feed.field1}} </td>
            <td> {{ station.last_feed.field2}} </td>
            <td> {{ station.last_feed.field3}} </td>
            <td> {{ station.last_feed.field4}} </td>
            <td> {{ station.last_feed.field5}} </td>
            <td> {{ station.updated_at}} </td>
        </tr>
      </tbody>
    </table>
  </div>

  

  <!-- <DatePicker/> -->

  <div class="selector_fecha">
      <label id="selecor_option">Seleccione la fecha en que desea los Reportes</label><br>
      <h4>Start DATE</h4>
      <input type="datetime-local" id="start" min="2023-02-01">
      <h4>Stop DATE</h4>
      <input type="datetime-local" id="stop" value="2023-05-06">
      <button @click="report">Traer Reporte</button>
</div>


</template>

<script>
// ACA SE AGREGAN LAS COMPONENTES UE USEMOS EN LA VISTA
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import TableHead from '@/components/TableHead.vue';
import DatePicker from '@/components/DatePicker.vue';

export default {
  name: 'Vista1',
  //ACÁ SE AGREGAN LAS COMPONENTES QUE VAMOS A UTILIZAR
  components: {
    HelloWorld,
    TableHead,
    DatePicker,
  },
  //ACÁ SE AGREGAN LOS DATOS ESTÁTICOS DE LA VISTA
  data() {
    return {
      STATIONS : [],
      Header_table : ['ESTACIÓN','Temperatura','Humedad','Material Particulado','UV','CO2','FECHA'],
      // start : new Date('2023-02-06'),
      // stop : new Date('2023-05-06'),
      fechaSeleccionada: null
    }
  },
  //ACÁ LAS FUNCIONES ESTÁTICAS DE LA VISTA
  methods: {
    async setup() {
    // This function must be executed only once!

    // GET STATIONS INFO
    const response = await fetch("https://raw.githubusercontent.com/Estacion-Meteorologica-UIS/thingspeak/main/stations.json");
    const stationsfile = await response.json();
    console.log(stationsfile)
    for (let index = 0; index < stationsfile.stations.length; index++) {
      const station = stationsfile.stations[index];
      const id = station.channelID;
      const key = station.readAPIKey;

      // Get other properties of station
      const response = await fetch(
          `https://api.thingspeak.com/channels/${id}/feeds.json?api_key=${key}&results=1` +
              "&timezone=America%2FBogota&status=true"
      );
      const data = await response.json();
      const { name, latitude, longitude, updated_at } = data.channel;
      console.log(data) 
      // const icon = L.icon({
      //     iconUrl: "https://icons.getbootstrap.com/assets/icons/exclamation-triangle-fill.svg",
      //     iconSize: [38, 95],
      // });
      // const marker = L.marker([latitude, longitude], { icon: icon }).addTo(map).bindPopup(name);

      this.STATIONS.push({
          name: name,
          id: id,
          key: key,
          location: [latitude, longitude],
          updated_at: updated_at,
          last_feed: data.feeds[0],
          // marker: marker,
      });
      }
      console.log(this.STATIONS)

    },
    updated() {
      
    },
    

  },
  //DIRECTIVA PARA CRGAR INFORMACION A LA PÁGINA ANTES DEL TEMPLATE
  created() {
    this.setup();
  },
  data_report(){
      let start_Date = document.getElementById("start").value;
      let stop_Date = document.getElementById("stop").value;
      // let tag = (rtipo=="Total" || rtipo=="Top")? null:document.getElementById(rtipo).value;
      console.log(stop_Date, start_Date);
   }
}
</script>

<style>
 /* ACA SE IMPORTAN LOS ESTILOS GLOBALES DE LA PÁGINA  */
/* @import "../assets/dashboard.css"; */

/* ACÁ SE HACEN LOS ESTILOS QUE SE UTILICEN ESPECIFICAMENTE PARA CADA VISTA O COMPONENTE */
table {
  table-layout: fixed;
  width: 100%;
  border-collapse: collapse;
  border: 3px solid greenyellow;
}


th, td {
  padding: 20px;
}

</style>