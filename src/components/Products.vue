<template>
	<div>
		<h1 class="title">All Products</h1>
    	<p>{{length}} products</p>
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
		      <tr v-for="product in products" track-by="id">
		        <td>{{product.name}}</td>
		        <td>{{product.description}}</td>
		        <td>${{product.price}}</td>
		        <td><button @click='addToCart(product)' class='button is-info'>Add to cart</button></td>
		      </tr>
		    </tbody>
		</table>
	</div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex'

export default {
  name: 'app',
  computed: mapGetters({
    products: 'allProducts',
    length: 'getNumberOfProducts'
  }),
  methods: mapActions([
    'addToCart'
  ])
}
</script>

<style lang="scss">

</style>
