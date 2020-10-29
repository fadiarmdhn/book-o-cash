<template>
  <div class="row">
    <div class="col-md-12"><product-info></product-info></div>
  </div>
</template>
<script>
import ProductInfo from '../components/Product/ProductInfo';
export default {
  name: 'product',
  components: {
    ProductInfo
  }
};
</script>
<style>
.table-transparent {
  background-color: transparent !important;
}
</style>
