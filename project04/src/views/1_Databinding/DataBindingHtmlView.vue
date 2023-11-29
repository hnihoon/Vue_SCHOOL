<template>
  <div> <!-- 최상위 태그가 있어야 함 (필수) -->
    <!-- HTML 바인딩 -->
    <div>{{ htmlString}} </div> <!-- innerText -->
    <div v-html="htmlString"></div> <!-- innerHTMl -->
  </div>
</template>

<script>

export default {
  data () {
    return {
      htmlString: '<p style="color:red">빨간색 문자</p>'
    }
  }
}
</script>
