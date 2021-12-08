<template>
    <ul>
        <todoitem v-for="item in todos" :key="item.id" :item="item" @dblclick="delTodo(index)"></todoitem>
    </ul>
</template>

<script>
import todoitem from './todoitem.vue'
export default {
    name: 'todo-list',
    props: ['todos'],
    components:{
        todoitem,
   },
   methods: {
    delToDo(index) {
      this.$emit("deltodo", { position: index });
    },
  },
}
</script>