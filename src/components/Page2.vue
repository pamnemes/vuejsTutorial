<template>
  <div class="page2">
page2<br />
<input v-model="message" placeholder="edit me">
<p>Message is: {{ message }}</p>
<text-word></text-word>
  </div>
</template>

<script>
export default {
  name: 'Page2',
  data () {
    return {
      msg: 'page2',
      seen: true,
      message: ''
    }
  },
  components: {
    'text-word': {
      template: '<div>text word </div>'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
