<template>
<div class="container">
  <div class="row h-box align-items-center">
    <div class="col-7">
      <div class="col-12 text-start" >
        <img  src="https://static.xx.fbcdn.net/rsrc.php/y8/r/dF5SId3UHWd.svg" width="250" height="100" >
        <div class="ps-4"><p class="text-start">Facebook te ayuda a comunicarte y compartir con las personas que forman parte de tu vida </p></div>
       </div>
    </div>
   <div class="col-4 mx-auto">
      <div class="card shadow p-2 ms-5">
        <form class="">
            <div class="form-group py-3 px-3">
              <input type="email" class="form-control f-custom"  placeholder="Correo o numero de telefono" v-model="palabra">
            </div>
             <div class="form-group pb-3 px-3">
               <input type="password" class="form-control f-custom" placeholder="Contraseña">
             </div>
              <div class="px-3"><button type="button" class="button-is w-100" @click="buscarPalabra(palabra)">Iniciar sesión</button>
              </div>
              <div class="form-group">
                 <div class="py-3"><a href="#">Olvidaste tu contraseña?</a></div>
               <div class="form-group pt-4 mb-3 mx-3 border-top">
                <div class=""><button type="button" class="button-ccn px-3">Crear cuenta nueva</button></div> 
               </div>
            </div>
        </form>
      </div>
      <div class="col-12 py-3 text-left">
        <p class="text-tittle-bussines ms-5">
          <a class="b-text" href="#">Crea una página</a> para un famoso, una marca o una empresa.
        </p>
      </div>
    </div>
 </div>
</div>
</template>

<script>
export default {
  name: 'HolaProyecto',
 
  data(){
    return {
      palabra:'',
      // contenedor: ["perro","gato","loro","agua",3,"mora","fresa","mango",4,"uva","vaca"],
        //  numeros: [5,8,6,7,1,12,45,1,57,32,25,10],
        //  numeros2: [],
    } 
  },

  mounted(){
  //  this.buscarPalabra('perro');
  },
  
  methods:{
    buscarPalabra(number){
      // let arraTemp = [];
     /* for(let i= 0; i < this.contenedor.length; i++){
        if(this.contenedor[i] === word){
          console.log('se encontro palabra ', this.contenedor[i] +'  en la posicion '+ i);
        }
      }

      console.log('no se encontro palabra');*/
    
      for (let i=0; i< this.numeros.length;i++){
          if(this.numeros[i]>10){
              this.numeros2.push(this.numeros[i] + parseInt(number))
          }
        }

         
          
          console.log(this.numeros2)
    },
  },

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.h-box{
  height: 30em;
}
.h1{
  color:#007bff;
}

p a{
  font-weight: bold;
  color: #1c1e21 !important;
}

.b-text:hover{
  text-decoration: underline !important;
}

.text-tittle-bussines{
  font-size: 14px;
  
}

.form-group .form-control.f-custom:focus {
  border-color: #1b74e4;
  box-shadow: 0 0 0 2px #e7f3ff !important;
  caret-color: #1b74e4;
  
}

.f-custom {
  border: 1px solid #dddfe2;
  color: #1d2129;
  font-family: Helvetica, Arial, sans-serif;
  font-size: 15px;
  height: 47px;
  line-height: 16px;
  padding: 0 8px;
  vertical-align: middle;
}

.button-is{
    background-color: #1877f2;
    border: none;
    border-radius: 6px;
    font-size: 20px;
    line-height: 47px;
    padding: 0 16px;
    color: #fff;
    font-weight: bold;
   
}

.button-ccn{
  font-size: 17px;
  line-height: 48px;
  border-radius: 6px;
  line-height: 47px;
  font-weight: bold;
  color: #fff;
  background-color:#42b72a ;
  border: none;
}

</style>