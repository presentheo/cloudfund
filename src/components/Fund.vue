<template>
  <ul class="list-wrap">
    <li class="list">
      <div class="card" v-for="(fund, index) in funds" :key="index">
        <h1>{{fund.title}}</h1>
        <p>{{fund.desc}}</p>
        <p>시작일 : {{fund.startDate}}</p>
        <p>종료일 : {{fund.endDate}}</p>
        <p>목표금액 : {{fund.fundGoal}}</p>
        <p>현재금액 : {{fund.fundCurrent}}</p>
      </div>
    </li>
  </ul>
</template>

<script lang="ts">
export default {
  name: 'Fund',
  data () {
    return {
      funds: [
        {
          title: 'Fund1',
          desc: 'Its a description of fund 1',
          startDate: 20190402,
          endDate: 20190430,
          fundGoal: 10000000,
          fundCurrent: 0
        }
      ]
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
