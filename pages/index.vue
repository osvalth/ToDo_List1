<template>
  <div class="container">

    <div class="cajas">
      <div class="input-group">
          <input class="form-control" placeholder="Agregar una nueva tarea" v-model="texto">
          <span class="input-group-btn">              
              <img src="/img/add.svg" @click="Agregar" style="width: 2.8em; min-width: auto;"/>
          </span>
      </div>
    </div>
    
    <div class="cajas">
      <div class="cajasOrd">
        <div class="list_Head contenedor-item">          
          <span>ToDo list by Iron Bit</span>          
          <img src="/img/recycle-bin.svg" @click="delete_full" style="width: 1.6em; min-width: auto;" />
        </div>
        <div class="body_List">
          <ul v-if="lista.length">
            <li v-for="todo in lista" :key="todo.id">
              <div class="contenedor-item">
                <span class="texto-item">{{ todo.nuevoTexto }}</span>                
                <img  src="/img/remove.svg" v-on:click="delete_one(todo.id)" style="width: 1.6em; min-width: auto;"/>
              </div>
              <br>
            </li>
          </ul>
          <p v-else>{{textoAux}}</p>
        </div>

      </div>
         
    </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      textoAux:'No hay ToDo´s, tomate un café !',
      texto:'',
      lista:[]
    }
  },
  methods: {
    Agregar: function(){
      this.lista.push({
        nuevoTexto: this.texto
      })
      this.texto='';
      console.log(this.lista)
    },
    delete_full: function(){
      this.lista.splice(0)
      console.log(this.lista)
    },
    delete_one:function(del1){
      this.lista.splice(del1, 1)
    }
  },


}
</script>

<style>
.container{
  max-width: 606px;
  display: flex;
  flex-direction: column;
  padding: 0em;
}
.cajas{
  margin: 1em;
}
.list_Head{
  display: grid;
  grid-template-columns: 28em 0em;
  grid-auto-flow: row;
  background-color: rgb(163, 255, 14);
  padding: 1.5em;
  border-radius: 0.5em 0.5em 0em 0em;
}
span{
  font: 1px;
  color: black;
}

.body_list{
  display: grid;
  grid-template-columns: 0.5px 0.5px;
  grid-template-rows: auto;
  grid-column-gap: 40px;
  background-color: rgb(255, 255, 255);
  border-radius:  0em 0em 0.5em 0.5em;
}

li {
  list-style:none; 
  border-radius: 5em;
}
p{
  text-align: center;
}
ul, p{
  display: grid;
  background-color: rgb(255, 255, 255);
  padding: 1.6em;
}
.texto-item{
  padding-right: 1rem;
  flex-grow: 1;
  word-break: break-all;
  justify-content: space-between;  
}
.contenedor-item{
  display: flex;
  justify-content: space-between;
  align-items:center;
  
}
</style>
