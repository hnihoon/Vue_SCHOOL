<template>
  <div>
    <!-- 1) DataBindingListView.vue -->
    <h3>배열 데이터 바인딩</h3>
    <hr>
    <div>
      <h2>목록</h2>
      <select name="" id="">
        <option value=""></option>
        <option v-for="city in cities" :key="city.code" :value="city.code">{{ city.title }}</option>
      </select> <!-- 반복문이 오면 유일한 값으로 :key 반드시 추가해야함 -->
    </div>
    <h4>표작성 후 목록 출력</h4>
    <table>
      <thead>
        <tr v-for="drink in drinkList" :key="drink.drinkId">
          <th>{{drink.drinkId}}</th>
          <th>{{drink.drinkName}}</th>
          <th>{{drink.price}}</th>
          <!-- <td>{{drink.qty}}</td> -->
          <td><input type="number" v-model="drink.qty"></td>
          <th>{{drink.price*drink.qty}}</th>
        </tr>
      </thead>
      <tbody>
      </tbody>
    </table>
  </div>
</template>

<script>

export default {
  data () {
    return {
      cities: [
        { title: '서울', code: '02' },
        { title: '부산', code: '051' },
        { title: '제주', code: '064' }
      ],
      drinkList: [
        { drinkId: '1', drinkName: '코카콜라', price: 700, qty: 1 },
        { drinkId: '2', drinkName: '오렌지주스', price: 1200, qty: 1 },
        { drinkId: '3', drinkName: '커피', price: 500, qty: 1 },
        { drinkId: '4', drinkName: '물', price: 700, qty: 1 },
        { drinkId: '5', drinkName: '보리차', price: 1200, qty: 1 },
        { drinkId: '6', drinkName: '포카리', price: 1000, qty: 1 },
        { drinkId: '7', drinkName: '뽀로로', price: 1300, qty: 1 }
      ]
    }
  }
}
</script>
