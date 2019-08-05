<template>
  <div>
    Todo
    <InputArea
      placeholder="add new todo"
      @handleAdd="handleAdd"
    />
    <Item
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @handleDelete="deleteNode"
    />
  </div>
</template>

<script>
import Item from './components/Item';
import InputArea from './components/InputArea';

const todos = [];

export default {
  name: 'todo-list',
  data: function () {
    return {
    name: String,
    todos,
  }
  },
  components: {
    InputArea,
    Item
  },
  methods: {
    handleAdd: function (value) {
      this.todos.push({ value, id: Math.round(Math.random() * (10**5)) })
    },
    deleteNode: function(idToRemove) {
      this.todos = this.todos.filter(({ id }) => id !== idToRemove);
    }
  }
}
</script>
