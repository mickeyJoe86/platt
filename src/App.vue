<template>
  <div id="app">
    <PlattHeader />
    <PlattNavList />
    <PlattBody />
    <PlattFooter />
  </div>
</template>

<script>
import PlattHeader from './components/PlattHeader'
import PlattNavList from './components/PlattNavList';
import PlattBody from './components/body/PlattBody';
import PlattFooter from './components/PlattFooter'

export default {
  name: 'app',
  components: {
    PlattHeader,
    PlattNavList,
    PlattBody,
    PlattFooter,
  }
}
</script>

<style lang="scss">
@import 'scss/index';
</style>
