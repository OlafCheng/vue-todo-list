<template>
<div>
  <span>{{ todo.value }}</span>
  <button @click="destory">X</button>
</div>
</template>

<script>
export default {
  props: {
    todo: {
      value: String,
      id: Number
    },
  },
  methods: {
    destory: function() {
      this.$emit('handleDelete', this.todo.id);
    }
  }
}
</script>
