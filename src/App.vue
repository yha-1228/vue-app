<template>
  <div id="app">
    <div class="container"><ProductTable /></div>
  </div>
</template>

<script>
import ProductTable from './components/ProductTable.vue';

export default {
  name: 'App',
  components: { ProductTable },
};
</script>

<style>
@import './styles/normalize.css';
@import './styles/base.css';
@import './styles/utils.css';
</style>
