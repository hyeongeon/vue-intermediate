<template>
  <div>
    <input class="inputBox" v-model="newTodoItem" type="text" v-on:keyup.enter="addTodo" />
    <button class="addBtn" v-on:click="addTodo">add</button>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      newTodoItem: "",
    };
  },

  methods: {
    addTodo: function () {
      localStorage.setItem(this.newTodoItem, this.newTodoItem);
      this.clearInput();
    },
    clearInput: function () {
      this.newTodoItem = "";
    },
  },
};
</script>

<style scoped>
input:focus {
  outline: none;
}

.inputBox {
  background: white;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}

.inputBox input {
  border-style: none;
  font-size: 0.9em;
}

.addBtn {
  color: white;
  vertical-align: middle;
}
</style>