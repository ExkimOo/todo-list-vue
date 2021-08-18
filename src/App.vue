<template>
  <div id="app">
    <Header />
    <Add
      @add-elem="addElem"
    />
    <List
      v-bind:todos="todos"
      @remove-elem="removeElem"
    />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import List from './components/List.vue'
import Add from './components/Add.vue'

export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, title: 'Learn JS', completed: false},
        {id: 2, title: 'Learn Vue', completed: false},
        {id: 3, title: 'Learn Frontend', completed: false},
      ]
    }
  },
  components: {
    Header,
    List,
    Add
  },
  methods: {
    removeElem(id) {
      this.todos = this.todos.filter(e => e.id !== id)
    },
    addElem(newElem) {
      this.todos.push(newElem)
    }
  }
}
</script>

<style>
* {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  box-sizing: border-box;
  font-size: 24px;
}
#app {
  text-align: center;
  color: #2c3e50;
}
</style>
