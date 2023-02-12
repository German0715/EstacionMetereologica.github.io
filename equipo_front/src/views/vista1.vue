<template>

  <!-- ENCARGADOS VISTA 1:GERMAN, ALEXANDRA, ALEJANDRO   -->

  <!-- EN EL TEMPLATE SE AGREGA TODO EL CÓDIGO HTML CONTENIDO EN LAS ETIQUETAS <body></body> DE LA RESPECTIVA VISTA -->

  <div class="home">
    <!-- ASÍ SE AGREGA EL CONTENIDO ESTÁTICO QUE ESTÁ EN EL ASSETS, LOGOS, IMÁGENES... ETC -->
    <img alt="Vue logo" src="../assets/estacion_ejemplo.jpg">

    <!-- ASÍ SE AGREGA UN COMPONENTE, EL msg ES LA INFORMACIÓN QUE LE ENVIAMOS AL COMPONENTE -->
    <HelloWorld msg="ULTIMA ACTUALIZACION"/> 
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

  <HelloWorld msg="REPORTES HISTORICOS"/> 
  <!-- <DatePicker/> -->

  <form @submit.prevent="reporte">
    <label>Seleccione la Estacion-Meteorologica-UIS de la cual desea Traer un Reporte:</label>
    <select  v-model="select_stations">
      <option v-for="(station, index) in STATIONS" :key="station.index">{{ station.name }}</option>
      <!-- <option>Todas</option> -->
    </select><br>
    <div class="selector_fecha">
      <label>Seleccione la Fecha de Inicio:</label>
      <input type="datetime-local" v-model="start">
      <label>Seleccione la Fecha de Cierre:</label>
      <input type="datetime-local" v-model="stop" ><br><br>
      <button @click="report"><label id="selecor_option">Traer Reportes del {{ start }} a {{ stop }}</label></button>
    </div>
  </form><br><br>
  
<Footer/>

</template>

<script>
// ACA SE AGREGAN LAS COMPONENTES UE USEMOS EN LA VISTA
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import TableHead from '@/components/TableHead.vue';
import DatePicker from '@/components/DatePicker.vue';
import Footer from '@/components/Footer.vue';

// import { response } from 'express';

export default {
  name: 'vista1',
  //ACÁ SE AGREGAN LAS COMPONENTES QUE VAMOS A UTILIZAR
  components: {
    HelloWorld,
    TableHead,
    DatePicker,
    Footer,
  },
  //ACÁ SE AGREGAN LOS DATOS ESTÁTICOS DE LA VISTA
  data() {
    return {
      STATIONS : [],
      REPORT : [],
      Header_table : ['ESTACIÓN','Temperatura','Humedad','Material Particulado','UV','CO2','FECHA'],
      start: '',
      stop: '',
      select_stations: '',
      thingspeak_data: [
        {
          Channel_ID: 2018613,
          API_Key: 'BCTCWXHKI63ABQTJ',
        },
        {
          Channel_ID: 2010447,
          API_Key: 'QFNSJOW53EFZ9Q3Y',
        },
        {
          Channel_ID: 2026237,
          API_Key: 'V5E461YNI6YLQMLP',
        },
        {
          Channel_ID: 2026008,
          API_Key: 'A1NNMO8RX9BH7DAG',
        },
      ]
    }
  },
  //ACÁ LAS FUNCIONES ESTÁTICAS DE LA VISTA
  methods: {
    async setup() {
    // This function must be executed only once!

    // GET STATIONS INFO
    // const response = await fetch("https://raw.githubusercontent.com/Estacion-Meteorologica-UIS/thingspeak/main/stations.json");
    // const stationsfile = await response.json();
    console.log(this.thingspeak_data)
    for (let index = 0; index < this.thingspeak_data.length; index++) {
      // const station = this.thingspeak_data[index].Channel_ID;
      const id = this.thingspeak_data[index].Channel_ID;
      const key = this.thingspeak_data[index].API_Key;

      // Get other properties of station
      const response = await fetch(
          // `https://api.thingspeak.com/channels/${id}/feeds.json?api_key=${key}&results=1` +
          //     "&timezone=America%2FBogota&status=true"
          `https://api.thingspeak.com/channels/${id}/feeds.json?api_key=${key}&results=1`
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
    async report(){
      let data_report = [];
      let date_start;
      let date_stop;
      let start_date;
      let stop_date;
      let start_year;
      let start_month;
      let start_day;
      let start_hour;
      let start_minute;
      let stop_year;
      let stop_month;
      let stop_day;
      let stop_hour;
      let stop_minute;

      console.log(this.start, this.stop);
      date_start = this.start.split('T');
      start_date = [
        start_year = date_start[0].split('-')[0],
        start_month = date_start[0].split('-')[1],
        start_day = date_start[0].split('-')[2],
        start_hour = date_start[1].split(':')[0],
        start_minute = date_start[1].split(':')[1],
      ];
      date_stop = this.stop.split('T');
      stop_date = [
        stop_year = date_stop[0].split('-')[0],
        stop_month = date_stop[0].split('-')[1],
        stop_day = date_stop[0].split('-')[2],
        stop_hour = date_stop[1].split(':')[0],
        stop_minute = date_stop[1].split(':')[1],
      ];
      console.log(this.select_stations,start_date,stop_date);
      if (this.select_stations!='Todas') {
        for (let index = 0; index < this.STATIONS.length; index++) {
          if (this.select_stations == this.STATIONS[index].name) {
            const response = await fetch(`https://api.thingspeak.com/channels/${this.STATIONS[index].id}/feeds.json?api_key=${this.STATIONS[index].key}&start=${start_year}-${start_month}-${start_day}%20${start_hour}:${start_minute}:00&end=${stop_year}-${stop_month}-${stop_day}%20${stop_hour}:${stop_minute}:59`);
            data_report = await response.json();
            console.log(data_report,(`https://api.thingspeak.com/channels/${this.STATIONS[index].id}/feeds.json?api_key=${this.STATIONS[index].key}&start=${start_year}-${start_month}-${start_day}%20${start_hour}:${start_minute}:00&end=${stop_year}-${stop_month}-${stop_day}%20${stop_hour}:${stop_minute}:59`));
          } 
        }
      }else{
        console.log('SELECCIONE ALGUNA ESTACION');
      }
      this.REPORT.push({
        station_info: {
          name: data_report.channel.name,
          id: data_report.channel.id,
          location: [data_report.channel.latitude, data_report.channel.longitude],
        }
      }) 
      for (let index = 0; index < data_report.feeds.length; index++) {
        this.REPORT.push({
        data : {
          time : data_report.feeds[index].created_at,
          Temperatura : data_report.feeds[index].field1,
          Humedad : data_report.feeds[index].field2,
          Material_Particulado : data_report.feeds[index].field3,
          UV : data_report.feeds[index].field4,
          CO2 : data_report.feeds[index].field5,
        }
      })        
      }
      
      
      console.log(this.select_stations,start_date,stop_date,data_report,this.REPORT);
    }
  },
  //DIRECTIVA PARA CRGAR INFORMACION A LA PÁGINA ANTES DEL TEMPLATE
  created() {
    this.setup();
  },

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
  border: 3px solid green;
}


th, td {
  padding: 20px;
}

</style>