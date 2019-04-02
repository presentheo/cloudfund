<template>
  <div>
    <Fund 
      v-for="(fund, index) in funds"
      :key="index"
      :fund="fund"
    ></Fund>
    <Order
      @make="makeOrder"
    ></Order>
  </div>
</template>

<script lang="ts">
import Fund from '../components/Fund.vue'
import Order from '../components/Order.vue'

export default {
  name: 'FundContainer',
  components: {
    Fund,
    Order
  },
  data() {
    return {
      funds: [
        {
          id: 1,
          title: 'Fund1',
          desc: 'Its a description of fund 1',
          startDate: 20190402,
          endDate: 20190430,
          fundGoal: 10000000,
          fundCurrent: 0,
          rewards: [
            {
              price: 50000,
              quantity: 500
            }
          ]
        }
      ]
    }
  },
  computed: {
    state: String
  },
  methods: {
    makeOrder(money, id) {

      this.funds.map((e) => {
        if (e.id == id){

          // 펀딩 성공
          if (money <= (e.fundGoal - e.fundCurrent) && this.getNow() >= e.startDate && this.getNow() <= e.endDate){
            e.fundCurrent += parseInt(money);
            alert(`${e.title} 상품에 ${money}원을 투자하셨습니다!`)
          }

          // 실패 - 최대금액 초과시
          if (money > (e.fundGoal - e.fundCurrent)){
            alert('최대 투자액을 초과했습니다!')
          }
          // 실패 - 펀딩 오픈 전
          if (this.getNow() < e.startDate){
            alert('펀딩 오픈 준비중입니다.')
          }
          // 실패 - 펀딩 마감
          if (this.getNow() > e.endDate){
            alert('펀딩이 마감되었습니다.')
          }
        }
      })
    },
    getNow() {
      var strDate = new Date();
      var yyyy = strDate.getFullYear();
      var mm = (strDate.getMonth() + 1 >= 10 ? '' : '0') + (strDate.getMonth() + 1);
      var dd = (strDate.getDate() >= 10 ? '' : '0') + strDate.getDate();
      // var hour = (strDate.getHours() >= 10 ? '' : '0') + strDate.getHours();
      // var minutes = (strDate.getMinutes() >= 10 ? '' : '0') + strDate.getMinutes();
      // var seconds = (strDate.getSeconds() >= 10 ? '' : '0') + strDate.getSeconds();

      return (yyyy + '' + mm + '' + dd);
    }
    
  }
}
</script>

<style>

</style>
