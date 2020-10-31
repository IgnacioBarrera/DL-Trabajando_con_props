<template>
  <div class="eliminar">
    <div v-if="enviandoTarea != 0">
      <ul v-for="(item, index) in enviandoTarea" :key="index">
        <li>{{item}}</li>
        <button type="submit" @click.prevent="quitarTarea">Eliminar</button>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Eliminar',
  props: {
    enviandoTarea: {
      type: Array,
      required: true,
    }
    },
  methods: {
      quitarTarea(index){
        let confirmar = confirm('Seguro desea eliminar esta tarea')
            if(confirmar){
                this.$emit('eliminarTarea', index);
            }
      }   
    },
}
</script>

<style scope>
ul {
  display: flex;
}
button {
  margin-left: 10px;
}
li {
  font-size: 15px;
  font-weight: 500;
}

</style>