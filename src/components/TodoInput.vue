<template>
  <div>
      <input v-model="newTodoItem" type="text" />
      <button v-on:click="addTodo">add</button>
  </div>
</template>

<script>
export default {
    data: function() {
        return {
            newTodoItem: ""
        }
    },

    methods: {
        addTodo: function() {
            localStorage.setItem(this.newTodoItem, this.newTodoItem);
            this.newTodoItem = "";
        }
    }
}
</script>

<style>

</style>