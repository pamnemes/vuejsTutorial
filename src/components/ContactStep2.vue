<template>
<content-template>
<template slot="header"> Content Us </template>
content
<div>
  <div>
     <div>
    <p>Name:{{fullname}}</p>
    <p>Email: {{ form.Email }}</p>
    <p>Comment: {{ form.Commentb }}</p>
    <button type="button" class="btn btn-danger" v-on:click="activeLinkBlack()" >black</button>
    <button type="button" class="btn btn-success">send</button>
  </div>
</div>
</div>
  {{alertextbox}}
  {{demo}}demo
  <p v-show="!enableSubmitBtn">กรอกข้อมูลไม่ครบ</p>
  </content-template>

</template>

<script>
export default {
  name: 'Contact',
  props: ['form'],
  data () {
    return {
      showform: true,
      alerttext: '',
      disableButton: true
    }
  },
  methods: {
    activeLinkBlack: function () {
      this.$emit('update:isPreview', false)
    }
  },
  computed: {
    enableSubmitBtn () {
      if (this.form.FirstName && this.form.LastName && this.form.Email) {
        return true
      } else {
        return false
      }
    },
    fullname: function () {
      var fullname = ''
      fullname = this.form.FirstName + ' ' + this.form.LastName
      return fullname
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
