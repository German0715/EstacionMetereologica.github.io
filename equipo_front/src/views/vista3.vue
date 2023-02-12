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

    <footer>
      <p>Estación Meteorológica UIS By Estudiantes UIS</p>
    </footer>
  </main>
</body>
</html>
</template>




<script>

</script>


<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}




header {
  width: 100%;
  height: 200px;
  overflow: hidden;
  position: relative;
}

header::before {
  content: '';
  position: absolute;
  border-top: 30px solid transparent;
  border-left: 400px solid white;
  bottom: 0;
}

header img {
  width: 100%;
  height: 199px;
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

footer {
  width: 100%;
  height: 80px;
  background: #314652;
  color: white;
  position: relative;
}

footer::before {
  content: '';
  position: absolute;

  top: 0;
}

footer p {
  padding: 30px;
}
</style>