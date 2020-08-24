<template>
  <div id="app">
    <ProductTable
      :products="[
        {
          id: '1',
          name: 'Incredible Concrete Shoes',
        },
        {
          id: '2',
          name: 'Small Rubber Cheese',
        },
        {
          id: '3',
          name: 'Ergonomic Soft Soap',
        },
      ]"
    />
  </div>
</template>

<script>
import ProductTable from './components/ProductTable.vue';

export default {
  name: 'App',
  components: { ProductTable },
};
</script>

<style></style>
