<template>
  <div id="app">
    <Font msg="Welcome to Your Vue.js + TypeScript App"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Font from './components/Font.vue';

export default Vue.extend({
  name: 'app',
  components: {
    Font
  }
});
</script>

<style>
#app {
}
</style>
