<template>
    <!-- ENCARGADOS VISTA 1:SOFIA, ERIKA   -->

<!-- HTML -->

<!-- Titulo -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Lato:ital@1&family=Roboto&display=swap" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GLhlTQ8iRABdZLl6O3oVMWSktQOp6b7In1Zl3/Jr59b6EGGoI1aFkw7cmDA6j6gD" crossorigin="anonymous">
  <HelloWorld class="tituloPri" msg="Estación meteorologica - UIS"/>
  <div class="Header">
    <img alt="estacion" class="imgPri" src="../imagenes_vista2/estacion.jpg">
    <HelloWorld class="txtTit" msg="Proyecto desarrollado con el fin de realizar mediciones y observaciones de los diferentes parámetros meteorológicos, tales como, temperatura, humedad, material particulado, calidad del aire y rayos UV. Esto, mediante el uso de sensores de bajo costo."/>
  </div>
  
<!-- Sensores -->
  <HelloWorld class="titulo" msg="Sensores"/>
  <div class="body">
    

    <div class="subBody">
      <img alt="sensorCo2" class="sensor" src="../imagenes_vista2/sensorCO2.jpg">
      <div class="contenedor">
        <HelloWorld class="titulo2" msg="SENSOR DE GAS DE CALIDAD DEL AIRE DE INTERIOR GY-SGP30 C02"/>
        <HelloWorld class="info" msg="SGP30 es un sensor de gas de óxido de metal con múltiples elementos de detección en un solo chip. Integra 4 elementos de detección de gas y tiene una señal de salida de calidad de aire totalmente calibrada. Además, SGP es fácil de integrar y puede integrar sensores de gas de óxido de metal en dispositivos móviles, abriendo nuevas posibilidades para el monitoreo ambiental en hogares inteligentes, electrodomésticos y aplicaciones IoT. Utilizado principalmente para la detección de formaldehído."/><a href="https://www.mouser.com/pdfdocs/Sensirion_Gas_Sensors_SGP30_Datasheet_EN-1148053.pdf" class="btn btn-success">Ver mas</a>
      </div>
    </div>

    <div class="subBody">
      <div class="contenedor">
        <HelloWorld class="titulo2" msg="SENSOR ÓPTICO DE POLVO GP2Y1010AU0F"/>
        <HelloWorld class="info" msg="GP2Y10 es un sensor de polvo por el sistema de detección óptica. Este dispositivo funciona mediante un sensor óptico, el cual se encuentra acondicionado para la percepción del aire, facilitando la detección de partículas de polvo, en su interior se encuentra un diodo emisor de luz infrarroja en diagonal y un fototransistor, de manera que se puede llevar a cabo la detección de polvo (partículas similares) en el aire, por lo general utilizado en un sistema de purificación de aire."/><a href="https://global.sharp/products/device/lineup/data/pdf/datasheet/gp2y1010au_e.pdf " class="btn btn-success">Ver mas</a>
      </div>
      <img alt="sensor" class="sensorPol" src="../imagenes_vista2/sensorpolvo.jpg">
    </div>

    <div class="subBody">
      <img alt="sensorUv" class="sensorUv" src="../imagenes_vista2/GY-ML8511-29.jpg">
      <div class="contenedor">
        <HelloWorld class="titulo2" msg="SENSOR DE LUZ UV GY-ML8511"/>
        <HelloWorld class="info" msg="El módulo ML8511 es un sensor de luz ultravioleta (UV), entrega una señal de voltaje analógica que depende de la cantidad de luz UV que detecta. Sensor ideal para proyectos de monitoreo de condiciones ambientales como el índice UV, Aplicaciones Meteorológicas, cuidado de la piel, medición industrial de nivel UV."/><a href="https://drive.google.com/file/d/1Ek6elSUxpDuPO6r4bkyYdG9hVlhc08TC/view?usp=sharing" class="btn btn-success">Ver mas</a>
      </div>
    </div>

    <div class="subBody">
      
      <div class="contenedor">
        <HelloWorld class="titulo2" msg="SENSOR DE TEMPERATURA Y HUMEDAD DTH11
"/>
        <HelloWorld class="info" msg="El DHT11 es un sensor digital de temperatura y humedad relativa de bajo costo y fácil uso. Utiliza un sensor capacitivo de humedad y un termistor para medir el aire circundante, y muestra los datos mediante una señal digital en el pin de datos (no posee salida analógica), el único inconveniente de este sensor es que sólo se puede obtener nuevos datos una vez cada 2 segundos. El sensor DHT11 se caracteriza por tener la señal digital calibrada, asegurando alta estabilidad y fiabilidad a lo largo del tiempo, puede medir la humedad en un rango desde 20% hasta 90% y temperatura en el rango de 0ºC a 50ºC."/><a href="https://cdn-learn.adafruit.com/downloads/pdf/dht.pdf " class="btn btn-success">Ver mas</a>
      </div>
      <img alt="sensorTem" class="sensorTem" src="../imagenes_vista2/dht11-ssensor.png">
    </div>

    <div class="subBody">
      <img alt="micro" class="micro" src="../imagenes_vista2/ESP-32.jpg">
      <div class="contenedor">
        <HelloWorld class="titulo2" msg="MICROCONTROLADOR ESP32"/>
        <HelloWorld class="info" msg="ESP32 es la denominación de una familia de chips SoC de bajo coste y consumo de energía, con tecnología Wi-Fi y Bluetooth de modo dual integrada. El ESP32 emplea un microprocesador Tensilica Xtensa LX6 en sus variantes de simple y doble núcleo e incluye interruptores de antena, balun de radiofrecuencia, amplificador de potencia, amplificador receptor de bajo ruido, filtros, y módulos de administración de energía."/><a href="https://www.espressif.com/sites/default/files/documentation/esp32_datasheet_en.pdf" class="btn btn-success">Ver mas</a>
      </div>
    </div>
  </div>

<!-- Materiales -->

  <HelloWorld class="titulo" msg="Materiales"/>
  <table class="table table-bordered">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Nombre</th>
      <th scope="col">Imagen</th>
      <th scope="col">Referencia</th>
      <th scope="col">Cantidad</th>
      <th scope="col">Valor</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Resistencia</td>
      <td><img alt="resis" class="resis" src="../imagenes_vista2/Resistencia.jpg"></td>
      <td><br>100 ohm <br><br> 1 kohm</td>
      <td><br>1 <br><br> 1</td>
      <td>400 COP</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Switch</td>
      <td><img alt="switch" class="switch" src="../imagenes_vista2/switch.png"></td>
      <td>3 conectores</td>
      <td>1</td>
      <td>1.500 COP</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Regulador</td>
      <td><img alt="regula" class="regula" src="../imagenes_vista2/regulador.jpg"></td>
      <td><br>L7805CV <br><br> LM1117T-ADJ</td>
      <td><br>1 <br><br> 1</td>
      <td><br> 1.100 COP<br><br>5.500 COP </td>
    </tr>

    <tr>
      <th scope="row">4</th>
      <td>Diodo zenner</td>
      <td><img alt="diodo" class="diodo" src="../imagenes_vista2/diodo_zenner.jpg"></td>
      <td>Tension de 12 V</td>
      <td>1</td>
      <td>154,70 COP</td>
    </tr>

    <tr>
      <th scope="row">5</th>
      <td >Diodo led</td>
      <td><img alt="led" class="led" src="../imagenes_vista2/diodo_led.jpg"></td>
      <td>Luz roja</td>
      <td>1</td>
      <td>100 COP</td>
    </tr>

    <tr>
      <th scope="row">6</th>
      <td >Capacitor ceramico</td>
      <td><img alt="ceramico" class="ceramico" src="../imagenes_vista2/Cap_ceramico.jpg"></td>
      <td>0.1 uF</td>
      <td>1</td>
      <td>200 COP</td>
    </tr>

    <tr>
      <th scope="row">7</th>
      <td>Condensador electrolitico</td>
      <td><img alt="conde" class="conde" src="../imagenes_vista2/condensador-electrolitico.jpg"></td>
      <td><br>10 uF <br><br> 220 nF</td>
      <td><br>1 <br><br> 1</td>
      <td><br>  300 COP<br><br>200 COP </td>
    </tr>

    <tr>
      <th scope="row">8</th>
      <td>Regleta de pines</td>
      <td><img alt="regleta" class="regleta" src="../imagenes_vista2/regleta-macho-macho.jpg"></td>
      <td>Macho-macho</td>
      <td>1</td>
      <td>500 COP</td>
    </tr>

    <tr>
      <th scope="row">9</th>
      <td>Regleta de pines</td>
      <td><img alt="regleta2" class="regleta2" src="../imagenes_vista2/Regleta-machoHembra.jpg"></td>
      <td>Macho-hembra</td>
      <td>1</td>
      <td>1.000 COP</td>
    </tr>

  </tbody>
</table>
 <footer>
      <p>Estación Meteorológica UIS By Estudiantes UIS</p>
    </footer>
</template>


<script>
import HelloWorld from '@/components/HelloWorld.vue';
import TableHead from '@/components/TableHead.vue';


export default {
  name: 'vista2',
  //ACÁ SE AGREGAN LAS COMPONENTES QUE VAMOS A UTILIZAR
  components: {
    HelloWorld,
    TableHead,
  },
}
</script>



<!-- Estilos -->

<style>

/* Header */

.tituloPri{
  font-size: 4rem;
  color: #004D53;
  padding: 15px 0;
  border-bottom: 5px solid #4AA873;
  border-top: 5px solid #4AA873;
  border-radius: 5px; 
}

.imgPri{
  border-radius: 7px;
}

.Header{
  width:80vw;
  display:inline-block;
  justify-content: center;
  align-items:center;
}

.txtTit{
  padding: 20px 0;
  text-align:justify;

}

/* Body */

.titulo{
  font-size: 3rem;
  color: #004D53;
  border-bottom: 5px solid #4AA873;
  padding: 0 0 20px 0;
}

.titulo2{
  font-size: 2.2rem;
  color: #004D53;
  
}

.info{
  text-align:justify;
  font-size: 1.5rem;
  padding: 0 0 15px 0;
}

.sensor{
  height:250px;
}

.sensorPol{
  height:350px;
}

.sensorUv{
  height:350px;
}

.sensorTem{
  height:450px;
}

.micro{
  height:250px; 
}


.body{
  width: 100%;
  margin: 40px 0;
  display:flex;
  justify-content:center;
  align-items:center;
  flex-direction: column;
}

.subBody{
  width:80%;
  display:flex;
  justify-content:center;
  box-shadow: 10px 10px #03242D;
  border-radius: 3px;
  margin: 10px 0;
  padding: 15px 0;
}

.contenedor{
  margin: 0 35px;
}

.resis{
  height: 150px;
}

.switch{
  height: 150px;
}

.regula{
  height: 150px;
}

.diodo{
  height: 150px;
}

.led{
  height: 120px;
}

.ceramico{
  height: 150px;
}

.conde{
  height: 120px;
}

.regleta{
  height: 150px;
}

.regleta2{
  height: 150px;
}

table{
  border: 3px solid greenyellow;
}

*{
font-family: 'Lato', sans-serif;
}


footer {
  clear: both;
	padding: 10px;
	text-align: center;
	border-top: 5px solid #4AA873;
  border-bottom: 5px solid #4AA873;
  background: #004D53;
  color: white;
}

</style>