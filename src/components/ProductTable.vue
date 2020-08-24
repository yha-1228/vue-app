<template>
  <table>
    <thead>
      <tr>
        <th>ID</th>
        <th>Name</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="product in products" :key="product.id">
        <td>{{ product.id }}</td>
        <td>{{ product.name }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: [products],
};
</script>

<style scoped></style>
