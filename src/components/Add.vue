<template>
    <div>
        <form v-on:submit.prevent>
            <input
                placeholder="Title..."
                v-model="title"
            >
            <button
                v-on:click="addElem"
                class="add"
            >
                Add
            </button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addElem() {
            if (this.title.trim()) {
                const newElem = {
                    id: Date.now(),
                    title: this.title,
                    completed: false
                }
                console.log(this.title)
                this.$emit('add-elem', newElem)
            }
        }
    }
}
</script>

<style>
form {
    margin: 20px 0;
}
input {
    padding: 0.5rem;
    width: 100vh;
}
.add {
    width: 20vh;
    padding: 0.5rem;
    font-weight: semi-bold;
}
</style>