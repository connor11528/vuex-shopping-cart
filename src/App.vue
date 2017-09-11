<template>
  <div id="app" class='container'>
    <add-product 
      :productToAdd='newProduct'
      v-on:form-submitted="saveProduct"></add-product>
    <product-list :products="products"></product-list>
  </div>
</template>

<script>
import uuid from 'uuid'
import AddProduct from './components/AddProduct.vue'
import ProductList from './components/ProductList.vue'

let initialData = {
  newProduct: {
    id: null,
    name: '',
    description: '',
    price: null
  }
}

export default {
  name: 'app',
  components: {
    AddProduct,
    ProductList
  },
  methods: {
    saveProduct(newProduct){
      newProduct.id = uuid.v4()
      this.products.push(newProduct)
      this.resetAddProductForm()
    },
    resetAddProductForm(){
      this.newProduct = initialData.newProduct
    }
  },
  data () {
    return {
      newProduct: initialData.newProduct,
      products: [
        {
          id: 'cc919e21-ae5b-5e1f-d023-c40ee669520c',
          name: 'COBOL 101 vintage',
          description: 'Learn COBOL with this vintage programming book',
          price: 399
        },
        {
          id: 'bcd755a6-9a19-94e1-0a5d-426c0303454f',
          name: 'Sharp C2719 curved TV',
          description: 'Watch TV like never before with the brand new curved screen technology',
          price: 1995
        },
        {
          id: '727026b7-7f2f-c5a0-ace9-cc227e686b8e',
          name: 'Remmington X mechanical keyboard',
          description: 'Excellent for gaming and typing, this Remmington X keyboard ' +
            'features tactile, clicky switches for speed and accuracy',
          price: 595
        }
      ]
    }
  }
}
</script>

<style lang="scss">

</style>
