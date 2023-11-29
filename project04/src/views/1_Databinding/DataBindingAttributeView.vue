<template>
  <div>
    <!-- 4) DetaBindingAttributeView.vue -->
    <h3> attribute 속성 데이터 바인딩</h3>

    <h4>readonly 속성</h4>
    <!-- readonly : 읽기만 가능 -->
    <input type="text" v-model="userId" readonly>

    <h4>readonly 속성(생략)</h4>
    <!-- readonly속성에서 v-model이면 양방향이 될 수 있음 -->
    <input type="text" v-model="userId">

    <h4>readonly 속성(생략)</h4>
    <!-- value 속성에 단방향 데이터 바인딩 할 수 있다.-->
    <input type="text" v-bind:value="userId">

    <h4>v-bind 생략</h4>
    <!-- v-bind 생략할 수 있다. -->
    <input type="text" :value="userId" readonly>

    <h4>src 속성</h4>
    <!-- 이미지 속성도 데이터 바인딩 할 수 있다 -->
    <img alt="" style="width: 100px; height: auto;" v-bind:src="imgSrc">

    <h4>disabled 속성 바인딩 - 검색어를 입력하지 않으면 조회버튼 비활성화</h4>
    <input type="search" v-model="txt1">
    <button  :disabled="txt1 === ''" >조회</button>

    <h4>style 속성 바인딩</h4>
      <div style="color: red; font-size: 30px">
      스타일 바인딩: 글씨는 red, 폰트크기: 20px
      </div>
      <div :style="style1">
        스타일 바인딩: 글씨는 green, 폰트크기:30px
      </div>
      <button @click="style1.color='blue'">색상바꾸기</button>

    <h4>class 속성 바인딩 - 다른 속성의 바인딩 방식과는 조금 다르다</h4>
      <div style="color:red">클래스 바인딩1</div>
      <div class="text-red">클래스 바인딩2</div>

      <!-- 선택자명이 두개의 단어로 구성되어 있으면 ' 기호 생략시 에러 -->
      <!-- <div :class="{text-red: true}">클래스 바인딩3</div> -->
      <div :class="{'text-red': true}">클래스 바인딩3</div>
      <div :class="{'text-red': false}">클래스 바인딩4</div>

      <div :class="{'text-red': true, active: true}">클래스 바인딩5</div>
      <div :class="{'text-red': false, 'active': true}">클래스 바인딩6</div>

      <!-- 변수로 대체가능 -->
      <div :class="{'text-red': hasError, 'active': isActive}">클래스 바인딩7</div>
      <!-- class를 배열로 저장 후 적용. 실무에서 그렇게 많이 사용하지는 않음 -->
      <div :class="class2">클래스 바인딩8</div>
  </div>
</template>

<script>

export default {
  data () {
    return {
      userId: 'korea',
      imgSrc: 'https://www.itwill.co.kr/css/wvtex/img/wvUser/logo.png',
      txt1: '',
      style1: { color: 'green', fontSize: '30px' },
      hasError: true,
      isActive: false,
      class2: ['active', 'text-red']
    }
  }
}

</script>

<!-- 현재 문서에서만 스타일 적용 -->
<style scoped>
  .text-red { color: red; }
  .active { background-color: greenyellow; font-weight: bold; }
</style>
