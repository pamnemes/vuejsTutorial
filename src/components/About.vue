<template>
<content-template>
  <template slot="header">Header</template>
  Content Body
</content-template>

</template>

<script>
import ContentTemplate from '@/components/ContentTemplate'
export default {
  name: 'About',
  data () {
    return {}
  },
  components: {
    ContentTemplate
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
