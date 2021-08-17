<template>
  <div id="app">
    <Header />
    <List
      v-bind:todos="todos"
    />
  </div>
</template>

<script>
import Header from './components/Header.vue'
import List from './components/List.vue'


export default {
  name: 'App',
  data() {
    return {
      todos: [
        {id: 1, title: 'Hello1', completed: false},
        {id: 2, title: 'Hello2', completed: false},
        {id: 3, title: 'Hello3', completed: false},
      ]
    }
  },
  components: {
    Header,
    List,
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
}
</style>
