<template>
<div class="container">
  <div class="row">
    <div class="col">
      First in DOM, no order applied
    </div>
    <div class="col order-12">
      Second in DOM, with a larger order
    </div>
    <div class="col order-1">
      Third in DOM, with an order of 1
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
    //this.nota();
  },
  
  methods:{
    nota(){
      if(this.calificacion<3.0){
        alert('deficiente')
      }else if (this.calificacion <3.5){
        alert('aceptable')
      }else if (this.calificacion<4.5){
        alert('sobresaliente')
      }else if(this.calificacion<=5){
        alert('excelente')
      }else{
        alert('la nota debe ser de 0 a 5')
      }
    }
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