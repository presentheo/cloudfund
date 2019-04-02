<template>
  <div id="app">
    <Fund></Fund>
    <Order></Order>
  </div>
</template>

<script>
import Fund from './components/Fund.vue'
import Order from './components/Order.vue'

export default {
  name: 'app',
  components: {
    Fund,
    Order
  }
}
</script>

<style>
  div{
    margin: 0;
    padding: 0;
  }
</style>
