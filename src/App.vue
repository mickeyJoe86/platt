<template>
  <div id="app">
    <PlattHeader />
    <PlattNavList />
    <PlattFooter />
  </div>
</template>

<script>
import PlattHeader from './components/PlattHeader'
import PlattFooter from './components/PlattFooter'
import PlattNavList from './components/PlattNavList';
export default {
  name: 'app',
  components: {
    PlattHeader,
    PlattFooter,
    PlattNavList
  }
}
</script>

<style lang="scss">
@import 'scss/index';
</style>
