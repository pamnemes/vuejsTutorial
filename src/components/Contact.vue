<template>
<content-template>
<template slot="header"> Content Us </template>
content
  <component v-bind:is="currentTabComponent" v-bind:is-preview.sync="isPreview" v-bind:form="form"></component>
  <div>
  </div>
  </content-template>

</template>

<script>
import ContentTemplate from '@/components/ContentTemplate'
import ContactStep1 from '@/components/ContactStep1'
import ContactStep2 from '@/components/ContactStep2'
export default {
  name: 'Contact',
  data () {
    return {
      showform: true,
      form: {},
      alerttext: '',
      disableButton: true,
      // currentTabComponent: 'ContactStep1',
      isPreview: false
    }
  },
  components: {
    'text-word': {
      template: '<div>text word </div>'
    },
    ContentTemplate,
    ContactStep1,
    ContactStep2
  },
  methods: {
    activeLinkNext: function () {
      if (this.form.FirstName && this.form.LastName && this.form.Email) {
        this.showform = false
        this.btncheck = false
        this.alerttext = 'กรอกข้อมูลครบ'
      } else {
        this.alerttext = 'กรอกข้อมูลไม่ครบ'
      }
    },
    activeLinkBlack: function () {
      this.showform = true
    }
  },
  computed: {
    currentTabComponent () {
      var currentTabComponent = 'ContactStep1'
      if (this.isPreview) currentTabComponent = 'ContactStep2'
      return currentTabComponent
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
