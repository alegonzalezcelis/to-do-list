<template>
  <div id="app">
    <div class="container">
      <h1 class="text-center mt-4 text-secondary">Crea una nueva tarea</h1>
      <div class="input-group mt-3">
        <input v-model="tarea" type="text" class="form-control" placeholder="Ingresa nueva tarea">
        <button @click="addTarea" class="btn btn-outline-secondary" type="button">Crear</button>
      </div>
      <h2 class="text-center my-5 text-secondary">Lista</h2>
      <ol>
        <div v-for="(tarea, i) in tareas" :key="i" class="lista">
          <li class="mb-3">{{ tarea }}</li> 
          <button @click="tareas.splice(index, 1)" type="button" class="btn btn-outline-danger btn-sm mb-3">Eliminar</button>
        </div>
        
      </ol>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data : () => ({
    tarea : '',
    tareas : []
  }),
  methods: {
    addTarea() {
      const { tarea } = this
      this.tareas.push(tarea)
      this.tarea = ''
    }
  }
}
</script>

<style>
.lista {
  display: flex;
  justify-content: center;
}

.lista > li {
  width: 50%;
}
</style>
