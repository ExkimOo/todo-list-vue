<template>
    <li>
        <input type="checkbox" v-on:change="todo.completed = !todo.completed">
        <strong>
            {{todo.id}}
        </strong>
        <span v-bind:class="{done: todo.completed}">
            {{todo.title}}
        </span>
        <button>х</button>
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        }
    }
}
</script>

<style>
li {
    font-size: 26px;
    width: 200px;
    border: 10px;
}

.done {
    text-decoration: line-through;
}
</style>
