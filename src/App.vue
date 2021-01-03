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
/* base */
/* ============================================================== */

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell,
    'Open Sans', 'Helvetica Neue', sans-serif;
  line-height: 1.7;
  color: rgb(30, 30, 30);
}

table {
  border-collapse: collapse;
}

/* utils */
/* ============================================================== */

.text-left {
  text-align: left;
}

.text-center {
  text-align: center;
}

.text-right {
  text-align: right;
}
</style>
