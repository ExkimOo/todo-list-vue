<template>
    <li>
        <span v-bind:class="{done: todo.completed}">
            <input class="checked" type="checkbox" v-on:change="todo.completed = !todo.completed">
            <strong>{{index + 1}}.</strong>
            {{todo.title}}
        </span>
        <button class="delete"
        v-on:click="$emit('remove-elem', todo.id)">
            х
        </button>
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true
        },
        index: Number
    }
}
</script>

<style>
li {
    font-size: 26px;
    width: 120vh;
    border: 10px;
    margin-bottom: 20px;
    border: 1px solid;
    padding: 5px;

    display: flex;
    align-items:center;
    justify-content: space-between;
}

.done {
    text-decoration: line-through;
}

.delete {
    border-radius: 50%;
    width: 40px;
    height: 40px;
    font-weight: bold;
    background-color: rgb(240, 240, 240);
    border: 2px solid;
}

.checked {
    width: 20px;
    height: 20px;
    margin-right: 10px;
}
</style>
