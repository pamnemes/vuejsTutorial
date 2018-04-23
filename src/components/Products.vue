<template>
<div>
  <!-- ใช้ v-for วน loop posts โดยใช้ id เป็นคีย์ -->
  <!-- <ul v-if="posts && posts.length">
    <li v-for="post of posts" :key="post.id">
      <div class="card">
        <div class="card-header">
          <p><strong>{{post.title}}</strong></p>
        </div>
      <p>{{post.body}}</p>
      </div>
    </li>
  </ul> -->
  <div v-show="!posts.length && !errors.length">loading...</div>
<div class="card mb-3" v-for="post of posts" :key="post.id">
  <div class="card-body">
    <h5 class="card-title">{{post.title}}</h5>
    <p class="card-text">{{post.body}}</p>
  </div>
</div>
  <div v-if="errors && errors.length> 0">
    {{errors[0].response.statusText}}
    <!-- response statusText มาจากอาเรย์ที่ส่งกลับมาในerrors เช็คค่าโดยการ {{errors}} -->
  </div>
</div>
</template>

<script>
import ContentTemplate from '@/components/ContentTemplate'
import axios from 'axios'

export default {
  name: 'About',
  data () {
    return {
      posts: [],
      errors: []
    }
  },
  components: {
    ContentTemplate
  },
  created () {
    axios.get(`http://jsonplaceholder.typicode.com/posts`).then(response => {
      // JSON responses are automatically parsed.
      console.log('response', response)
      // ไว้ดูค่าดีบัค f12 แล้วหาresponse
      this.posts = response.data
    }).catch(e => {
      this.errors.push(e)
    })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
