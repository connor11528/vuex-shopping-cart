<template>
  <form>
    <div class="field">
      <label for="productName" class='label'>Product name</label>
      <input type="text" v-model="productToAdd.name" class="input" id="productName" maxlength="32" placeholder="Enter product name">
    </div>
    <div class="field">
      <label for="productDescription" class='label'>Product description <small class="help">(optional)</small></label>
      <textarea class="textarea" v-model="productToAdd.description" id="productDescription" rows="3" maxlength="128" placeholder="Enter description"></textarea>
    </div>
    <div class="field">
      <label for="price" class='label'>Price</label>
      <input type="number" v-model="productToAdd.price" class="input" id="price" placeholder="Enter Price" number>
    </div>
    <button type="submit" v-on:click.prevent="onSubmit" class="button is-primary">Add product</button>
  </form>
</template>

<script>
export default {
  props: ['productToAdd'],
  methods: {
    onSubmit () {
      this.$emit('form-submitted', this.productToAdd);
    }
  }
}
</script>