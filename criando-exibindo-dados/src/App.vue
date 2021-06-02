<template>
  <div id="app">
    <h1 v-once v-text="titulo"></h1>
    <h2>{{ subtitulo }}</h2>
    <div v-if="tarefas.length <= 0">
      Não há tarefas
    </div>
    <div v-if="tarefas.length > 0">
      Existem {{tarefas.length}} tarefas

      <ul>
        <li v-for="tarefa in tarefas">
          {{ tarefa }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ef-tarefas',
  data () {
    return {
      titulo: 'Listagem de tarefas',
      subtitulo: 'Defina uma descrição',
      tarefas: []
    }
  },
  mounted () {
    setTimeout( () => {
      this.titulo = "Novo título"

      this.tarefas = ['tarefa 1', 'tarefa 2', 'tarefa 3', 'tarefa 4']
    }, 3000 )
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
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
