<template>
  <input
    v-model="thing"
    @keydown.enter="handleValue"
  />
</template>

<script>
export default {
  data: function(params) {
    return {
      thing: ''
    }
  },
  methods: {
    handleValue: function() {
      this.$emit('handleAdd', this.thing);
      this.thing = '';
    }
  }
}
</script>
