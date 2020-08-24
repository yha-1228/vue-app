<template>
  <table class="product-table">
    <thead>
      <tr class="table-row">
        <th class="table-cell text-right">ID</th>
        <th class="table-cell text-left">Brand</th>
        <th class="table-cell text-left">Category</th>
        <th class="table-cell text-left">Name</th>
        <th class="table-cell text-right">Price</th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="product in products"
        :key="product.id"
        class="table-row"
        v-bind:class="product.stocked ? 'warn' : !undefined"
      >
        <td class="table-cell text-right">{{ product.id }}</td>
        <td class="table-cell text-left">{{ product.brand }}</td>
        <td class="table-cell text-left">{{ product.category }}</td>
        <td class="table-cell text-left">{{ product.name }}</td>
        <td class="table-cell text-right">{{ product.price }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    axios
      .get('https://5e6736691937020016fed762.mockapi.io/products')
      .then((response) => {
        this.products = response.data;
      });
  },
};
</script>

<style scoped>
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

.warn {
  color: red;
}

/* components */
/* ============================================================== */

.product-table {
  width: 100%;
}

.table-row {
  border-bottom: 1px solid lightgray;
}

.table-cell {
  padding: 10px;
}

/* utils */
/* ============================================================== */

.align-left {
  text-align: left;
}

.warn {
  color: red;
}
</style>
