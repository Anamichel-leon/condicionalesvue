<template>
    <div class="container">
      <div class="row mt-4">
        <div>
          <h4>Eventos Clik</h4>
          <button @click="clic" class="btn btn-danger" type="button">Dale clic</button> 
          <button @click="SoyButon" class="btn btn-warning mx-2" type="button">Dale clic 2</button>
        </div>
      
       <div>
        <h4>Eventos Change</h4>
      <label class="input-group-text" for="">Ingresa tu nombre</label>
      <input class="form-control mt-2" type="text" id="nombre" @change="nombreE">
      <p>El nombre ingresado es: <strong>{{ nombre }}</strong></p>
       </div>
       <div>

      <h3>Evento de mouseenter y mouseleave</h3>
      
      <div class="text-center"
        style="color: #ffff; width: 300px; height: 200px; background-color: black; text-align:center; padding: 15px; border-radius:14px;"
        @mouseenter="mostrarMensaje" @mouseleave="ocultarMensaje">
        <p>Pase el mouse</p> 
        <p>{{ mensaje }}</p>
         </div>
      </div>    
    </div>
</div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        nombre: '',
        mensaje: '',
      };
    },
    methods: {
      clic() {
        alert("Gracias por darle clic");
      },
      SoyButon() {
        alert("Gracias por darle clic 2");
      },
      nombreE(event) {
        this.nombre = event.target.value;
      },
      mostrarMensaje() {
        console.log("Mouse dentro");
        this.mensaje = "El mouse está dentro del rectángulo";
      },
      ocultarMensaje() {
        console.log("Mouse fuera");
        this.mensaje = "El mouse está fuera del rectángulo";
      }
    } 
  };
  </script>
  
  <style scoped>
  /* Aquí puedes agregar estilos personalizados */
  </style>
  