<template>
<div class="container">
  <div class="row">
    <div class="col-6">
      <h1 class="">facebook</h1>
      <p class="">facebook te ayuda a comunicarte y compartir con las personas que forman parte de tu vida </p>
    </div>
  <div class="col">
    <form>
     <div class="form-group py-3">
       <input type="email" class="form-control"  aria-describedby="emailHelp" placeholder="Correo o numero de telefono">
     </div>
     <div class="form-group pb-3">
       <input type="password" class="form-control" placeholder="contraseña">
     </div>
     <button type="submit" class="btn btn-primary">Iniciar sesión</button>
     <div class="form-group py-2">
      <label>olvidaste tu contraseña?</label>
      <div class="form-group py-2">
        <button type="button" class="btn btn-success">Crear cuenta nueva</button>
      </div>
     </div>
    </form>
   </div>
 </div>
</div>
</template>

<script>
export default {
  name: 'HolaProyecto',
 
  data(){
    
       //this.calificacion = prompt('digite la nota ')
       
  },

  mounted(){
   
  },
  
  methods:{
    
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>