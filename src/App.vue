<template>
  <div id="app">
    <Tarea @mandandoTarea='actualizandoTarea'/>
    <Eliminar :enviandoTarea='nuevasTareas' @eliminarTarea='eliminaTarea'/>
  </div>
</template>

<script>
import Tarea from './components/Tarea.vue'
import Eliminar from './components/Eliminar.vue'

export default {
  name: 'App',
  data() {
    return {
      nuevasTareas: []
    }
  },
  components: {
    Tarea,
    Eliminar
  },
  methods: {
    actualizandoTarea(work){
      console.log(work);
      this.nuevasTareas.push(work);
    },
    eliminaTarea(index){
      this.nuevasTareas.splice(index,1);
    }
  },
}
</script>

<style>
#app {
  margin: 0 auto;
}
</style>
