<template>
<body>
    <div id="app">
        <h1> {{ title }} </h1>
        <todolist v-if="todos.length" :todos="todos" @deltodo="delTodo"></todolist>
        <p v-else>No hay tareas que mostrar</p>
        <Addtodo @add-Todo='anyadirTodo'></Addtodo>
       <Deletelist @delete-all='deleteAllTodos'></Deletelist>
    </div>
</body>
</template>

<script>
import todolist from './components/todolist.vue'
import Deletelist from './components/Deletelist.vue'
import Addtodo from './components/Addtodo.vue'

export default {
  name: 'App',
  components: {
    todolist,
    Deletelist,
    Addtodo,
  },
  data() {
    return {
        title: 'Hola a todos',
      todos: [
        { 
          id: 1,
          descrip: "Learn JavaScript", 
          done: false 
        }, { 
          id: 2,
          descrip: "Learn Vue", 
          done: false 
        }, { 
          id: 3,
          descrip: "Play around in JSFiddle", 
          done: true 
        }, { 
          id: 4,
          descrip: "Build something awesome", 
          done: true 
        }
      ]
    }
  },
  methods: {
    deleteAllTodos(){
      this.todos = []
    },
    anyadirTodo(newTarea) {
      this.todos.push(newTarea)
    },
    delTodo(index) {
      this.todos.splice(index.position, 1)
    }  
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
