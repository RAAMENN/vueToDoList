<template>
  <li @click="handleDelete">{{todoItem}}</li>
</template>

<script>
export default {
  props: ['index', 'todoItem'],
  methods: {
    handleDelete () {
      this.$emit('delete', this.index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
