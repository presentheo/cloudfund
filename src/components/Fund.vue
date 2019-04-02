<template>
  <ul class="list-wrap">
    <li class="list">
      <div class="card">
        <h1>{{fund.title}}</h1>
        <p>{{fund.desc}}</p>
        <p>시작일 : {{fund.startDate}}</p>
        <p>종료일 : {{fund.endDate}}</p>
        <p>목표금액 : {{fund.fundGoal}}</p>
        <p>현재금액 : {{fund.fundCurrent}}</p>
        <p>{{percentage}}% 모금됨</p>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">
export default {
  name: 'Fund',
  props: {
    fund: {
      type: Object,
      required: true
    }
  },
  computed: {
    percentage: function(){
      return (Math.floor(this.fund.fundCurrent/this.fund.fundGoal*100))
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .list-wrap{
    display: flex;
  }
  .list{
    display: flex;
  }
  .card{
    border: 1px solid #ddd;
  }



</style>
