<template>
  <div id="app">
    <PlattHeader />
    <PlattFooter />
  </div>
</template>

<script>
import PlattHeader from './components/PlattHeader.vue'
import PlattFooter from './components/PlattFooter.vue'

export default {
  name: 'app',
  components: {
    PlattHeader,
    PlattFooter
  }
}
</script>

<style lang="scss">
@import 'scss/index';
</style>
