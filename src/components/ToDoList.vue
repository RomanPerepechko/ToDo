<template>
    <div class="main-block">
        <div v-for="toDoElement in toDoList" :key="toDoElement.id" class="do-element">
            <input @click="checkToDo(toDoElement.id)" type="checkbox">
            <span>{{ toDoElement.title }}</span>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        data: Array
    },
    methods: {
        checkToDo(id) {
            this.$emit('check-to-do', id)
        }
    },
    computed: {
        toDoList: function () {
            return this.data.filter(el => el.check === false)
        }
    },
}
</script>

<style scoped>
.do-element {
    display: flex;
    height: 50px;
    border: 1px solid #000;
    width: 300px;
    margin-bottom: 20px;
    align-items: center;
}
</style>