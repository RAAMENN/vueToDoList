<template>
  <div id="app">
    <input type="text" v-model="inputValue">
    <button @click="handleClick">Update</button>
    <ul>
      <todo-item v-for="(item, index) of list" :key="index" :todoItem="item" :index="index" @delete="handleDelete"></todo-item>
    </ul>
  </div>
</template>

<script>
import todoItem from './components/TodoItem'
export default {
  components: {
    'todo-item': todoItem
  },
  data () {
    return {
      inputValue: '',
      list: []
    }
  },
  methods: {
    handleClick () {
      this.list.push(this.inputValue)
      this.inputValue = ''
    },
    handleDelete (index) {
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
</style>
