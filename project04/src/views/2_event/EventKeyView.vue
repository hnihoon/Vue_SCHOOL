<template>
  <div>
    <h3>key 이벤트</h3>
    <input type="search" v-model="searchText" @keyup.enter="doSearch">
    <button @click="doSearch">조회</button>
    <!-- keyup이벤트의 세부 속성들 -->
    <!-- .enter -->
    <!-- .tab -->
    <!-- .delete -->
    <!-- .space -->
    <!-- .ctrl.enter-->
    <hr>

    <!-- $event 현재 시점에서 발생한 이벤트값 -->
    <input type="search" v-model="searchText" @keyup="checkEnter($event)">
  </div>
</template>

<script>

export default {
  data () {
    return {
      searchText: ''
    }
  },
  methods: {
    doSearch () {
      alert(this.searchText)
    },
    checkEnter (event) {
      if (event.keyCode === 13) { // 엔터키를 눌럿다면 (엔터 == 아스키코드 13)
        this.doSearch()
      }
    }
  }
}
</script>
