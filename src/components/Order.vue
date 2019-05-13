<template>
  <div>
    <input
      type="number"
      v-model="id">
    <span>번 상품에</span>
    <input
      type="number"
      v-model="money">
    <span>원을 투자합니다</span>
    <button
      @click="$emit('make', money, id)"
    >확인</button>
  </div>
  
</template>

<script lang="ts">
export default {
  data(){
    return {
      money: 0,
      id: 1
    }
  }
}
</script>

<style>

</style>
