<template>
  <div> <!-- 최상위 태그가 있어야 함 (필수) -->
    <!-- 문자열 데이터 바인딩 -->
    <h1>Hello {{userName}}</h1>
    <p>{{message}}</p>
  </div>
</template>

<script>

export default {

  data () {
    return {
      // 본문과 바인딩에 필요한 변수를 선언
      userName: 'itwill',
      message: '아이티윌 교육센터'
    }
  }
}
</script>
