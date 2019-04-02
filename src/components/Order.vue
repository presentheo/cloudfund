<template>
  <div>
    <input
      type="number"
      v-model="id">
    <input
      type="number"
      v-model="money">
    <button
      @click="$emit('make', money, id)"
    >투자하자</button>
  </div>
  
</template>

<script lang="ts">
export default {
  data(){
    return {
      money: 0,
      id: 0
    }
  }
}
</script>

<style>

</style>
