<template>
    <ul>
        <ListElem
            v-for="todo of todos"
            v-bind:todo="todo"
            v-bind:key="todo.id"
        />
    </ul>
</template>

<script>
import ListElem from './ListElem.vue'
export default {
    props: ['todos'],
    components: {
        ListElem,
    }
}

</script>

<style>
ul {
    list-style: none;
    margin: 0;
    padding: 0;
    
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>