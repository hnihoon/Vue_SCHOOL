<template>
  <div>
    <!-- 3) DataBindingInputView.vue -->
    <h3>input 바인딩 - 양방향</h3>
    <input type="text" v-model="userId">

    <h3>이벤트</h3>
    <!-- <button onclick="myFunction()"></button> -->
    <button @click="myFunction">클릭</button>
    <button @click="changeData">변경</button>

    <h3>숫자 바인딩</h3>
    <input type="text" v-model="num1">
    <input type="text" v-model="num2">
    <span>{{num1 + num2}}</span>
    <hr>
    <input type="text" v-model="num3">
    <input type="text" v-model="num4">
    <span>{{num3 + num4}}</span>

    <h3>select 바인딩</h3>
    <select name="" id="" v-model="selectedCity">
      <option value=""></option>
      <option value="02">서울</option>
      <option value="051">부산</option>
      <option value="064">제주</option>
    </select>

    <h3>checkbox 바인딩</h3>
    <div>
      <input type="checkbox" id="html" value="HTML" v-model="favoriteLang">
      <label for="html">HTML</label>
    </div>
    <div>
      <input type="checkbox" id="css" value="CSS" v-model="favoriteLang">
      <label for="css">CSS</label>
    </div>
    <div>
      <input type="checkbox" id="js" value="JS" v-model="favoriteLang">
      <label for="js">JavaScript</label>
    </div>
    <div>선택한 과목 : {{favoriteLang}}</div>

    <h3>radio 바인딩</h3>
    <div>
      <input type="radio" id="food1" value="짜장면" v-model="favoriteFood">
      <label for="food1">짜장면</label>
    </div>
    <div>
      <input type="radio" id="food2" value="짬뽕" v-model="favoriteFood">
      <label for="food1">짬뽕</label>
    </div>
    <div>
      <input type="radio" id="food3" value="탕수육" v-model="favoriteFood">
      <label for="food1">탕수육</label>
    </div>
    <div>좋아하는 음식 : {{ favoriteFood }}</div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      userId: 'itwill.co.kr',
      num1: 0,
      num2: 0,
      num3: 0,
      num4: 0,
      selectedCity: '051', // 02|051|064
      // favoriteLang: [] // 여러개 선택이 가능한 값은 반드시 배열로 선언한다.
      favoriteLang: ['JS'], // 초기값 설정
      favoriteFood: ''
    }
  },
  methods: {
    myFunction () { // Function 생략
      alert(this.userId) // ; 입력시 오류
    },
    changeData () {
      this.userId = 'KOREA'
    }
  }
}
</script>
