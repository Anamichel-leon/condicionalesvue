<script>
export default {
    data () {
        return {
            alumnos:[
                { nc:21620112, nombre: 'Ana', carrera:'ISC'},
                { nc:21620112, nombre: 'Michel', carrera:'IGE'},
                { nc:21620112, nombre: 'Leon', carrera:'ISC'},

            ]
        }
    }
}
</script>
<template>
<div class="container">
    <h3 class="mt-4">LISTA DE ALUMNOS</h3>
    <ul>
        <li v-for="alumno in alumnos" :key="alumno.nc"> 
       <strong>{{ alumno.nombre }} </strong> -
       <strong>{{ alumno.carrera }} </strong>
    </li>
    </ul>  
</div>
</template>
<style>
h3{
    color: white;
    background-color: rgb(37, 186, 212);
    border-radius: 25px;
    padding: 15px;
    text-align: center;
    font-style:italic;
}
ul{
  list-style-type: none; 
  padding: 0;
}
li{
    color: rgb(235, 227, 229);
background-color: black;
border-radius: 25px;
padding: 15px;
margin: 10px;
background-image: url('https://imgs.search.brave.com/bKBjtjcTKc8f9EIcrzg7r1speO9_Ik4FrLYWG9wO960/rs:fit:500:0:0:0/g:ce/aHR0cHM6Ly9waXhs/ci5jb20vaW1hZ2Vz/L2dlbmVyYXRvci9w/aG90by1nZW5lcmF0/b3Iud2VicA');
background-size: cover; /* Esto ajusta la imagen para que cubra todo el fondo */
background-position: center; /* Esto centra la imagen */
font-size: 25px;
}
</style>