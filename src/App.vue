<template>
  <div id="app">
    <PlattHeader />
    <PlattBody />
    <PlattFooter />
  </div>
</template>

<script>
import PlattHeader from './components/header/PlattHeader';
import PlattBody from './components/body/PlattBody';
import PlattFooter from './components/footer/PlattFooter';

export default {
  name: 'app',
  components: {
    PlattHeader,
    PlattBody,
    PlattFooter,
  }
}
</script>

<style lang="scss">
@import 'scss/index';
</style>
