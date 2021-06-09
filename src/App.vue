<template>
  <div id="app">
    <Nav />
    <AlbumsContainer />
  </div>
</template>

<script>
import Nav from './components/Nav.vue';
import AlbumsContainer from './components/AlbumsContainer.vue'

export default {
  name: 'App',
  components: {
    Nav,
    AlbumsContainer,
  }
}
</script>

<style lang="scss">
  @import './style/general.scss';

</style>
