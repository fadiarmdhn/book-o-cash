<template>
  <div class="row">
    <div class="col-md-12"><cash-flow></cash-flow></div>
  </div>
</template>

<script>
import CashFlow from '../components/Reporting/CashFlow.vue';
export default {
  name: 'reporting',
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
