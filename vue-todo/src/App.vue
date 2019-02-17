<template>
  <div id="app">
    <HeaderComponent></HeaderComponent>
    <InputComponent v-on:add-todo="addTodo"></InputComponent>
    <ListComponent v-bind:props-todo-items="todoItems" v-on:removeItem="removeItem"></ListComponent>
    <FooterComponent v-on:removeItemAll="removeItemAll"></FooterComponent>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      todoItems: [] 
    }
  },
  components: {
    HeaderComponent: HeaderComponent,
    InputComponent: InputComponent,
    ListComponent: ListComponent,
    FooterComponent: FooterComponent
  },
  methods: {
    addTodo: function(item) {
      localStorage.setItem(item, item);
      this.todoItems.push(item);
    },
    removeItem: function(item, index) {
      this.todoItems.splice(index, 1);
      localStorage.removeItem(item);
    },
    removeItemAll: function() {
      this.todoItems = [];
      localStorage.clear();
    }
  },
  created: function() {
    for (var i=0; i<localStorage.length; i++) {
      this.todoItems.push(localStorage.key(i));
    }
  }
}

import HeaderComponent from "./components/HeaderComponent.vue"
import InputComponent from "./components/InputComponent.vue"
import ListComponent from "./components/ListComponent.vue"
import FooterComponent from "./components/FooterComponent.vue"
</script>

<style>

</style>
