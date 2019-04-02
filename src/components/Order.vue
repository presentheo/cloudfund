<template>
  <div>
    <input
      type="number"
      v-model="money">
    <button
      @click="makeOrder"
    >투자하자</button>
  </div>
  
</template>

<script>
export default {
  data(){
    return {
      money: Number
    }
  },
  methods: {
    makeOrder() {
      alert(this.money);
    }
  }
}
</script>

<style>

</style>
