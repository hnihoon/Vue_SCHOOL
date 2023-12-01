<template>
  <div>
    <!-- MemoListView.vue -->
    <!-- 웹서버와 데이터 통신 -->
    <!-- ● Backend : SpringBoot기반 (spring9_memo프로잭트 참조) -->
    <h3>방명록</h3>
    <p>
      <button class="btn btn-primary" @click="getList">목록</button>
    </p>
      <ul class="list-group">
      <li v-if="memoList.length == 0" class="list-group-item">게시물이 없습니다</li>
      <li v-for="memo in memoList" class="list-group-item" :key="memo.memono">{{ memo.subject }}<span class="badge">{{ memo.readcnt }}</span></li>
    </ul>
  </div>
</template>

<script>

export default {
  data () {
    return {
      memoList: []
    }
  },
  methods: {
    getList () {
      // fetch() 자바스크립트 기반의 서버와 데이터 통신
      fetch('http://localhost:9095/memolist').then((response) => {
        if (response.ok) {
          return response.json()
        }
      }).then((json) => {
        this.memoList = json
      })
    }
  }
}
</script>

<style>
  @import 'https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css';
</style>
