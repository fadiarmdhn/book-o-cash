<template>
  <div class="row">
    <div class="col-12">
      <!-- Big Chart -->
      <big-chart></big-chart>

      <overview></overview>
    
      <!-- Small Chart -->
      <small-chart></small-chart>
    
      <!--Orderan Terbaru-->
      <new-order></new-order>
    </div>
  </div>
</template>

<script>
import BigChart from '../components/Dashboard/BigChart'
import SmallChart from '../components/Dashboard/SmallChart'
import NewOrder from '../components/Dashboard/NewOrder'
import Overview from '../components/Dashboard/Overview'

export default {
  name: 'dashboard',
  components: {
    BigChart,
    SmallChart,
    NewOrder, 
    Overview
  }
}
</script>

<style></style>
