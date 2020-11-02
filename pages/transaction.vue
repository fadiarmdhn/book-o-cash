<template>
  <div class="row">
    <div class="col-md-12"><transaction></transaction></div>
  </div>
</template>

<script>
import CashFlow from '../components/Reporting/Transaction.vue';
export default {
  name: 'transaction',
  components: {
    CashFlow
  }
};
</script>

<style>
.table-transparent {
  background-color: transparent !important;
}
</style>
