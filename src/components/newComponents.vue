<template>
  <div class="container" >
      <div class="row col-12 py-5">
        <h1>Registro de personas </h1>
      </div>
      <!-- Button trigger modal -->
      <div class="row col-2 ms-0 fs-1 pb-2">
        <button type="button" class="btn btn-primary" @click="agregar()" data-bs-toggle="modal" data-bs-target="#exampleModal" data-bs-whatever="@mdo"><i class="fa fa-plus" aria-hidden="true"></i>
        Agregar Persona
      </button>
      </div>
      

      <!-- Modal -->
        <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog">
            <div class="modal-content">
              <div class="modal-header">
                <h1 class="modal-title fs-5" id="exampleModalLabel">Nuevo registro</h1>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
              </div>
              <div class="modal-body">
                <form>
                  <!-- Foto -->
                  <div class="col-12">
                    <div class="box m-auto border border-3" ><img v-if="form.foto? true: false" class="img" :src="form.foto" alt="" id="ff"></div>
                    <div class="py-4"><button  @click="subirFoto()" class="btn btn-primary" type="button">Subir fotografia</button></div>
                    <input class="d-none" type="file" @change="onChange($event)" accept="image" id="foto">
                  </div>
                  <div class="col-12 mb-3">
                    <!-- <registro> -->
                    <input type="text" class="form-control" v-model="form.nombre" id="nombre" placeholder="Nombre">
                  </div>
                  <div class="col-12 mb-3">
                    <!-- <label for="message-text" class="col-form-label">Message:</label> -->
                    <input class="form-control" type="text" v-model="form.apellido" id="apellido" placeholder="Apellido">
                  </div>
                  <div class="col-12 mb-3">
                    <!-- <label for="message-text" class="col-form-label">Message:</label> -->
                    <input class="form-control" type="number" v-model="form.edad" id="message-text" placeholder="Edad">
                  </div>
                </form>
              </div>
              <div class="modal-footer">
                <button type="button" class="btn btn-secondary" @click="resetForm" data-bs-dismiss="modal">Cerrar</button>
                <button type="button" class="btn btn-primary" @click="guardar" data-bs-dismiss="modal">Agregar</button>
              </div>
            </div>
          </div>
        </div>
      
    <div class="card">
      <div class="card-body">
          <table class="table table-striped">
        <thead>
          <tr>
            <th scope="col-2">#</th>
            <th scope="col-2">Nombre</th>
            <th scope="col-2">Apellido</th>
            <th scope="col-2">Edad</th>
            <th scope="col-2">Accion</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(data, index)  in lista " :key="index">
            <th scope="row">{{ index + 1}}</th>
            <td>{{data.nombre}}</td>
            <td>{{data.apellido}}</td>
            <td>{{data.edad}}</td>
            <td><a href="#" data-bs-toggle="modal" @click="edit(index)" data-bs-target="#exampleModal" ><i class="fa fa-pencil" title="Editar"   aria-hidden="true"></i></a>  <a href="#" @click="borrar(index)" ><i class="fa fa-trash" title="Borrar" aria-hidden="true"></i></a></td>
          </tr>
        </tbody>
      </table>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: 'newProject',
   data(){
    return {
      file:'',
      form: {
        foto:'',
        nombre: '',
        apellido: '',
        edad: ''
      },
      lista: [],
      action: '',
      indice:0,
    }
  },

  mounted(){
  },
  
  methods:{
    subirFoto(){
       document.getElementById("foto").click();
    },
    onChange(event){
      
      // if (event.target.files.length==0) return ;
      this.file = event.target.files[0];
      this.form.foto = URL.createObjectURL(this.file)
      // let reader = new FileReader();
      // reader.readAsDataURL(file);
      
      console.log("event",this.form.foto)
    },

    guardar(){
      if(this.action=='agregar'){
       this.lista.push({
        foto: this.form.foto,
        nombre: this.form.nombre,
        apellido:this.form.apellido,
        edad: this.form.edad
      })  
       
      } else {
     this.lista[this.indice].nombre = this.form.nombre
     this.lista[this.indice].apellido=this.form.apellido
     this.lista[this.indice].edad=this.form.edad
     this.lista[this.indice].foto=this.form.foto
      }
      this.resetForm()
    },

    resetForm () {
      this.form.foto = ''
      this.form.nombre = ''
      this.form.apellido=''
      this.form.edad=''
    },

    edit(index){
     this.form.nombre=this.lista[index].nombre 
     this.form.apellido=this.lista[index].apellido
     this.form.edad=this.lista[index].edad
     this.form.foto=this.lista[index].foto
     
     this.action='editar'
     this.indice=index
    },

    agregar(){
    this.action='agregar'
    },

    borrar(index){
     this.lista.splice(index,1)
     
    },
  },
}
</script>

<style>
.box{
    height: 10em;
    width: 10em;
    border-radius: 10em;
    background: #f0f2f5;
}
.img{
    height: 10em;
    width: 10em;
    border-radius: 10em;
}

</style>
