<template>
  <div id="app">
    <HeaderComponent></HeaderComponent>
    <InputComponent></InputComponent>
    <ListComponent></ListComponent>
    <FooterComponent></FooterComponent>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    HeaderComponent: HeaderComponent,
    InputComponent: InputComponent,
    ListComponent: ListComponent,
    FooterComponent: FooterComponent
  }
}

import HeaderComponent from "./components/HeaderComponent.vue"
import InputComponent from "./components/InputComponent.vue"
import ListComponent from "./components/ListComponent.vue"
import FooterComponent from "./components/FooterComponent.vue"
</script>

<style>

</style>
