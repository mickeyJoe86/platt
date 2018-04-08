<template>
  <div id="app">
    <PlattHeader msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import PlattHeader from './components/PlattHeader.vue'

export default {
  name: 'app',
  components: {
    PlattHeader
  }
}
</script>

<style lang="scss">
@import 'scss/index';
</style>
