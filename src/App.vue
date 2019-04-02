<template>
  <div id="app">
    <FundContainer></FundContainer>
  </div>
</template>

<script>
import FundContainer from './containers/FundContainer'

export default {
  name: 'app',
  components: {
    FundContainer
  }
}
</script>

<style>
  div{
    margin: 0;
    padding: 0;
  }
</style>
