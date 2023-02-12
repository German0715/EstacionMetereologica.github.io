<template>
    <div>
        <footer>
            <p>Estación Meteorológica UIS By Estudiantes UIS</p>
        </footer>
    </div>
</template>

<script>
// ASÍ ES COMO RECIBIMOS LOS DATOS EN DE UN COMPONENTE parenthesizedExpression, EN ESTE CASO LA VISTA1
export default {
  name: 'Footer',
  props: {
    msgs: {
        type: Array,
        required: true, 
    }
  }
}
</script>

<style>
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