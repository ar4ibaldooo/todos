<template>
  <div id ="app">
    <h1>Test application</h1>
    <AddApp
      @add-todo="addTodo"
    />
    <hr>
    <ListApp
    v-bind:todos="todos"
    @remove-todo="removeTodoItem"
    />
  </div>


</template>

<script>
import ListApp from '@/components/ListApp'
import AddApp from '@/components/AddApp'
export default {
  name: 'App',
  data () {
      return {
          todos: [
              {id: 1, title: 'купить хлеб', completed: false},
              {id: 2, title: 'купить maslo', completed: false},
              {id: 3, title: 'купить bulku', completed: false}
          ]
      }
  },
  methods: {
    removeTodoItem(id){
      this.todos = this.todos.filter(t=>t.id !== id)
    },
    addTodo(todo){
            this.todos.push(todo)
         }
  },
  components: {
    ListApp,
    AddApp
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
