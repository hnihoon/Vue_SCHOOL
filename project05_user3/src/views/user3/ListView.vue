<template>
    <div>
        <h1>사용자 목록 (ListView)</h1>
        <p>
            <button class="btn btn-danger" @click="getData">AXIOS모듈 테스트</button>
            &nbsp;
            <router-link to="/user3/create" class="btn btn-success">사용자 추가</router-link>
        </p>
    </div>
</template>

<script>
// 주의사항) axios모듈 임포트하고 사용하지 않으면 에러 발생 'axios is defined but never used
import axios from 'axios'
export default {
  data () {
    return {
    }
  },
  methods: {
    getData () {
      axios
        .get('http://localhost:9095/test')
        .then((response) => {
          console.log(response)
        })
        .catch((error) => {
          console.log(error)
        })
    }
  }
}
</script>

<style>
  @import 'https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css';
</style>
