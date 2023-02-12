<template>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Card Perfil</title>
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Montserrat&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="style.css">

</head>
<body>
  <h3>Nuestra gente:</h3>
  <div class="container-card">
	
  <div class="card">
    <figure>
      <img src="../assets/img1.jpg">
    </figure>
    <div class="contenido-card">
      <h3>GRUPO B1</h3>
      <p>Estudiantes del programa de Ingeniería Electronica de la Universidad Industrial de Santander, matriculados al curso de Instrumentación Electrónica (Grupo B1), dirigidos por el profesor Julián Rodríguez. <br>Para más información, visite su sitio web.</p>
      <a href="https://sites.google.com/e3t.uis.edu.co/proyecto-semestre-grupo-b1-y-b/equipo" target="_blank">Leer más </a>
    </div>
  </div>
  <div class="card">
	<figure>
		<img src="../assets/grupod1.jpg">
	</figure>
	<div class="contenido-card">
		<h3>GRUPO D1</h3>
		<p>Estudiantes del programa de Ingeniería Electronica de la Universidad Industrial de Santander, matriculados al curso de Instrumentación Electrónica (Grupo D1), dirigidos por el profesor Julián Rodríguez. <br>Para más información, visite su sitio web.</p>
		<a href="https://sites.google.com/e3t.uis.edu.co/proyectod1d2/equipos" target="_blank">Leer más</a>
	</div>
</div>
</div>
  <main class="nosotros">
    <header>
      
    </header>

    <section>
      <h2>Universidad Industrial de Santander</h2>
      <p>NIT: 890.201.213-4</p>
      <h3>Síganos</h3>
      <ul>
        <li><a href="https://www.facebook.com/uisenlinea" class="fa fa-facebook" target="_blank"></a></li>
        <li><a href="https://www.instagram.com/UIS/" class="fa fa-instagram" target="_blank"></a></li>
        <li><a href="https://twitter.com/UIS" class="fa fa-twitter" target="_blank"></a></li>
        <li><a href="https://www.linkedin.com/school/universidad-industrial-de-santander/" class="fa fa-linkedin" target="_blank"></a></li>
      </ul>
      <br>
      <h3>Línea de atención nacional</h3>
      <p>+57 01 8000 111 641</p>
      <h3>Teléfono</h3>
<p>+57 (607) 634 4000</p>
    </section>

    <Footer/>
  </main>
</body>
</html>
</template>




<script>
import HelloWorld from '@/components/HelloWorld.vue';
import TableHead from '@/components/TableHead.vue';
import Footer from '@/components/Footer.vue';


export default {
  name: 'vista3',
  //ACÁ SE AGREGAN LAS COMPONENTES QUE VAMOS A UTILIZAR
  components: {
    HelloWorld,
    TableHead,
    Footer,
  },
}
</script>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}




header {
  width: 100%;
  height: 50px;
  overflow: hidden;
  position: relative;
}

header::before {
  content: '';
  position: absolute;
  border-top: 30px solid transparent;
  border-left: 100px solid white;
  bottom: 0;
}

header img {
  width: 100%;
  height: 100px;
}

section {
  padding: 100px;
  overflow: hidden;
  text-align: center;
}

section h2 {
  margin: .2em 0;
}

section p {
  margin: .5em 0;
}

ul li {
  list-style: none;
  display: inline-block;
  margin: .3em .1em;
}

ul li a {
  text-decoration: none;
  color: white;
  background: #314652;
  width: 30px;
  height: 30px;
  line-height: 30px !important;
  border-radius: 50%;
  transition: all .3s ease-in-out;
}

ul li a:hover {
  transform: scale(1.2);
}


.container-card{
	width: 100%;
	display: flex;
	max-width: 1100px;
	margin: auto;
}
.title-cards{
	width: 100%;
	max-width: 1080px;
	margin: auto;
	padding: 20px;
	margin-top: 20px;
	text-align: center;
	color: #7a7a7a;
}
.card{
	width: 100%;
	margin: 20px;
	border-radius: 6px;
	overflow: hidden;
	background:#fff;
	box-shadow: 0px 1px 10px rgba(0,0,0,0.2);
	transition: all 400ms ease-out;
	cursor: default;
}
.card:hover{
	box-shadow: 5px 5px 20px rgba(0,0,0,0.4);
	transform: translateY(-3%);
}
.card img{
	width: 100%;
	height: 210px;
}
.card .contenido-card{
	padding: 15px;
	text-align: center;
}
.card .contenido-card h3{
	margin-bottom: 15px;
	color: #7a7a7a;
}
.card .contenido-card p{
	line-height: 1.8;
	color: #6a6a6a;
	font-size: 14px;
	margin-bottom: 5px;
}
.card .contenido-card a{
	display: inline-block;
	padding: 10px;
	margin-top: 10px;
	text-decoration: none;
	color: #2fb4cc;
	border: 1px solid #2fb4cc;
	border-radius: 4px;
	transition: all 400ms ease;
	margin-bottom: 5px;
}
.card .contenido-card a:hover{
	background: #2fb4cc;
	color: #fff;
}
@media only screen and (min-width:320px) and (max-width:768px){
	.container-card{
		flex-wrap: wrap;
	}
	.card{
		margin: 15px;
	}
}
</style>