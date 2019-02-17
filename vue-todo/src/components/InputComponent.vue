<template>
    <div>
      <input v-model="todoItem" v-on:keyup.enter="addTodo">
      <button v-on:click="addTodo">add</button>
    </div>
</template>
<script>
export default {
    data: function() {
        return {
            msg: "This is a InputComponent",
            todoItem: ""
        }
    },
    methods: {
        addTodo: function() {

            var todoItem = this.todoItem && this.todoItem.trim();
            if (todoItem != "") {
                this.$emit("add-todo", todoItem);
                this.todoItem = "";
            }
        }
    }
}
</script>
<style scoped>

</style>
