<template>
  <div class="row">
    <div class="col-md-12"><add-inventory></add-inventory></div>
  </div>
</template>

<script>
import AddInventory from '../components/Inventory/AddInventory';

export default {
  name: 'inventory',
  components: {
    AddInventory
  }
};
</script>
<style>
.table-transparent {
  background-color: transparent !important;
}
</style>
