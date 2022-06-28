<template>
    <div class="form-add">
        <input v-model="titleToDo" type="text">
        <button @click="createToDo()">добавить</button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            titleToDo: ''
        }
    },
    methods: {
        createToDo() {
            if (this.titleToDo.trim() !== '') {
                this.$emit('create-to-do', this.titleToDo)
                this.titleToDo = ''
            }
        }
    }
}
</script>

<style scoped>
</style>