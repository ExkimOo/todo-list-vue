<template>
    <ul>
        <ListElem
            v-for="(todo, i) of todos"
            v-bind:todo="todo"
            v-bind:key="todo.id"
            v-bind:index="i"
            v-on:remove-elem="removeElem"
        />
    </ul>
</template>

<script>
import ListElem from './ListElem.vue'
export default {
    props: ['todos'],
    components: {
        ListElem,
    },
    methods: {
        removeElem(id) {
            this.$emit("remove-elem", id)
        }
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