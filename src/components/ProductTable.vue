<template>
  <Container>
    <div v-if="error">Error: {{ error }}</div>
    <div v-else-if="!isLoaded">Loading...</div>
    <div v-else>
      <table class="table">
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
            v-bind:class="product.stocked ? 'table-row--warn' : !undefined"
          >
            <td class="table-cell text-right">{{ product.id }}</td>
            <td class="table-cell text-left">{{ product.brand }}</td>
            <td class="table-cell text-left">{{ product.category }}</td>
            <td class="table-cell text-left">{{ product.name }}</td>
            <td class="table-cell text-right">{{ product.price }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </Container>
</template>

<script>
import Container from './Container.vue';
import { productsUrl } from '../constants';

export default {
  data() {
    return {
      isLoaded: false,
      products: [],
      error: null,
    };
  },
  mounted() {
    fetch(productsUrl)
      .then((res) => res.json())
      .then((result) => {
        this.isLoaded = true;
        this.products = result;
      })
      .catch((error) => {
        this.isLoaded = true;
        this.error = error;
      });
  },
  components: { Container },
};
</script>

<style scoped>
/* components */
/* ============================================================== */

.table {
  width: 100%;
}

.table-row {
  border-bottom: 1px solid lightgray;
}

.table-row--warn {
  color: gray;
}

.table-cell {
  padding: 8px;
}
</style>
