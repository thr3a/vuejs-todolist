<template>
  <div id="app">
    <h1>TODO app</h1>
    <ul>
      <li v-for="(task, index) in tasks">
        {{ task }}<input type='button' value='x' v-on:click="remove(index)">
      </li>
    </ul>
    <input type='text' v-model='newTask'>
    <input type='button' value='追加' v-on:click="add">
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      newTask: '',
      tasks : [
        '掃除','洗濯', '買い物'
      ]
    }
  },
  methods: {
    add: function(e) {
      this.tasks.unshift(this.newTask);
      this.newTask = '';
    },
    remove: function(index) {
      this.tasks.splice(index, 1);
    }
  }
}
</script>

<style lang="scss">
</style>
