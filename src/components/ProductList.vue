<template>
  <table class="table is-striped">
    <thead>
      <tr>
        <th>Name</th>
        <th>Description</th>
        <th>Price</th>
        <th></th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="product in products" track-by="id" v-on:click.prevent="onEdit(product)">
        <td>{{product.name}}</td>
        <td>{{product.description}}</td>
        <td>${{product.price}}</td>
        <td><a href='#' v-on:click.prevent.stop="onRemove(product.id)" class='button is-danger'>remove</a></td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: ['products'],
  methods: {
    onEdit (product) {
      this.$emit('edit', product)
    },
    onRemove (productId) {
      this.$emit('remove', productId)
    }
  }
}
</script>