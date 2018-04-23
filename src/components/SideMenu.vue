<template>
  <div class="page2">
<ul>
  <!-- <li class="list-group-item" v-bind:class="{ active: homeActive}" v-on:click="activeLink('homeActive')"><router-link to="/page2"><h5>home</h5></router-link></li> -->
<router-link tag="li" class="list-group-item" to="/page2" v-bind:class="{ active: homeActive}" v-on:click.native="activeLink('homeActive')"><h5>home</h5></router-link>
  <!-- <li class="list-group-item" v-bind:class="{ active: aboutActive}" v-on:click="activeLink('aboutActive')"><router-link to="/about"><h5>about us</h5></router-link></li>
  <li class="list-group-item" v-bind:class="{ active: contactActive}" v-on:click="activeLink('contactActive')"><router-link to="/contact"><h5>contact</h5></router-link></li>
  <li class="list-group-item" v-bind:class="{ active: productsActive}" v-on:click="activeLink('productsActive')"><router-link to="/products"><h5>products us</h5></router-link></li> -->
<router-link tag="li" class="list-group-item" to="/about" v-bind:class="{ active: aboutActive}" v-on:click.native="activeLink('aboutActive')"><h5>about</h5></router-link>
<router-link tag="li" class="list-group-item" to="/contact" v-bind:class="{ active: contactActive}" v-on:click.native="activeLink('contactActive')"><h5>contact</h5></router-link>
<router-link tag="li" class="list-group-item" to="/products" v-bind:class="{ active: productsActive}" v-on:click.native="activeLink('productsActive')"><h5>products</h5></router-link>
</ul>
  </div>
</template>

<script>
export default {
  name: 'SideMenu',
  data () {
    return {
      homeActive: false,
      aboutActive: false,
      contactActive: false,
      productsActive: false
    }
  },
  methods: {
    activeLink: function (activeMenu) {
      this.homeActive = false
      this.aboutActive = false
      this.contactActive = false
      this.productsActive = false
      this[activeMenu] = true
    }
  },
  created () {
    console.log('router', this.$route.name)
    // this.$router.name
    switch (this.$route.name) {
      case 'Home':
        this.homeActive = true
        break
      case 'About':
        this.aboutActive = true
        break
      case 'ContactHome':
        this.contactActive = true
        break
      case 'Products':
        this.productsActive = true
        break
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* ul > li.active >a {
    color: #cfc;
} */
ul > li {
   cursor: pointer;
}

</style>
