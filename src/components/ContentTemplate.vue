<template>
<div>
  <header>
    <h2><slot name="header"></slot></h2>
  </header>
  <p align = 'left'>
    <slot></slot>
  </p>
</div>
</template>

<script>
export default {
  name: 'About',
  data () {
    return {}
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
