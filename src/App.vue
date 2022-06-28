<template>
  <div>
    <ToDoList @check-to-do="checkToDo" :data="toDoList" />
    <FormAdd @create-to-do="addToDo" />
  </div>


</template>

<script>
import ToDoList from './components/ToDoList.vue'
import FormAdd from './components/FormAddToDo.vue'
export default {
  data() {
    return {
      toDoList: [
        { id: 1, title: 'Сделать что-то1', check: false },
        { id: 2, title: 'Сделать что-то2', check: false },
        { id: 3, title: 'Сделать что-то3', check: false },
        { id: 4, title: 'Сделать что-то4', check: false },
        { id: 5, title: 'Сделать что-то5', check: false },
        { id: 6, title: 'Сделать что-то6', check: false },
        { id: 7, title: 'Сделать что-то6', check: false },
      ]
    }
  },
  methods: {
    addToDo(payload) {
      this.toDoList.push({ id: Math.random(), title: payload, check: false })
    },
    checkToDo(id) {
      this.toDoList.forEach(el => {
        if (el.id == id) {
          el.check = true
        }
      }
      )
    }
  },
  components: {
    ToDoList,
    FormAdd
  }
}
</script>

<style scoped>
</style>
