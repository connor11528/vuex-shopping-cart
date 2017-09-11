<template>
  <table class="table is-striped">
    <thead>
      <tr>
        <th>Name</th>
        <th>Description</th>
        <th>Price</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="product in products" track-by="id">
        <td>{{product.name}}</td>
        <td>{{product.description}}</td>
        <td>${{product.price}}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: ['products']
}
</script>