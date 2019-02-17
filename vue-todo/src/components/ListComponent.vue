<template>
    <section>
      <ul>
          <li v-for="(todoItem, index) in propsTodoItems" v-bind:key="index">  <!-- 상위컴포넌트에서 케밥케이스로 보냈지만 여기선 카멜케이스로 받음(propsTodoItems) -->
              {{todoItem}}
              <button v-on:click="removeItem(todoItem, index)">remove</button>
          </li>
      </ul>
    </section>
</template>
<script>
export default {
    props: ["props-todo-items"],
    methods: {
        removeItem: function(value, index) {
            this.$emit("removeItem", value, index);
        }
    }
}
</script>
<style scoped>

</style>
