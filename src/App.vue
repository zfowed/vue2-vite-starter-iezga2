<template>
  <div id="app">
    <Demo />
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'
import Demo from './components/Demo.vue'

export default defineComponent({
  name: 'App',
  components: {
    Demo,
  },
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
