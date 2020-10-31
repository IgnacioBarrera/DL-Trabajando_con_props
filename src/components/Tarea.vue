<template>
  <div>
    <form @submit.prevent="agregandotareas">
      <label>Tarea</label>
      <input type="text" placeholder="Ingrese una nueva tarea" v-model="tarea">
      <button type="submit">Añadir</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Tarea',
  data() {
    return {
      tarea: "",
    }
  },
  methods: {
    agregandotareas(){
      let enviandoTarea = this.tarea;
      this.$emit('mandandoTarea', enviandoTarea);
      this.tarea = "";
    }
  },
}
</script>

<style scoped>
label {
  margin-right: 10px;
  font-size: 30px;
  font-weight: bold;
}
</style>
