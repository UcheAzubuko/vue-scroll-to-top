<template>
  <section>
    <AppButton/>
  </section>
</template>

<script>
import AppButton from './components/AppButton.vue';


export default {
  name: 'App',
  components: {
    AppButton
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
