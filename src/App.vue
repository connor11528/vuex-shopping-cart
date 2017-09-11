<template>
  <div id="app">
    <product-list></product-list>
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue'

export default {
  name: 'app',
  components: {
    ProductList
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="scss">

</style>
