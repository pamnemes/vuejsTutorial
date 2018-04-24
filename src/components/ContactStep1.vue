<template>
<content-template>
<template slot="header"> Content Us </template>
content
<div>
  <div>
  <div class="form-group">
  <label for="usr">First Name:</label>
  <input type="text" class="form-control" id="FName" v-model="form.FirstName">
  <p>Message is: {{ form.FirstName }}</p>
</div>
<div class="form-group">
  <label for="pwd">Last Name:</label>
  <input type="text" class="form-control" id="Lname" v-model="form.LastName">
    <p>Message is: {{ form.LastName }}</p>
</div>
<div class="form-group">
  <label for="pwd">E-mail:</label>
  <input type="email" class="form-control" id="Email" v-model="form.Email">
  <p>Message is: {{ form.Email }}</p>
</div>
<div class="form-group">
  <label for="comment">Comment:</label>
  <textarea class="form-control" rows="5" id="comment" v-model="form.Commentb"></textarea>
</div>
      <!-- <p>alert:{{alerttext}}</p> -->
<button type="button" class="btn btn-success" v-on:click="activeLinkNext()" v-bind:disabled="!enableSubmitBtn">Next</button>
{{enableSubmitBtn}}
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
    activeLinkNext: function () {
      this.$emit('update:isPreview', true)
    }
  },
  computed: {
    enableSubmitBtn () {
      if (this.form.FirstName && this.form.LastName && this.form.Email) {
        return true
      } else {
        return false
      }
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
