<template>
  <div class="inputBox shadow">
    <input v-model="newTodoItem" type="text" v-on:keyup.enter="addTodo" />
    <span class="addContainer">
        <i v-on:click="addTodo" class="fas fa-plus"></i>
    </span>
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
      if (this.newTodoItem) {
          this.$emit('addTodoItem', this.newTodoItem);
          this.clearInput();
      }
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
  background: aliceblue;
  height: 50px;
  line-height: 50px;
  border-radius: 5px;
}
.inputBox input {
  border-style: none;
  font-size: 0.9rem;
}
.addContainer {
  float: right;
  background: linear-gradient(to right, #6478FB, #8763FB);
  display: block;
  width: 3rem;
  border-radius: 0 5px 5px 0;
}
.addBtn {
  color: white;
  vertical-align: middle;
}
</style>