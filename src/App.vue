<template>
  <div>
      <!--Setting Up Router-->
      <!--add header-->
      <app-header></app-header>
      <router-view></router-view>
  </div>
</template>

<script>
// Imports
import showBlogs from './components/showBlogs.vue';
import listBlogs from './components/listBlogs.vue';
import header from './components/header.vue'; //third, import header
export default {
  components: {
      'app-header': header //fourth, add component of the header
  },
  data () {
      return {
      }
  },
  methods: {
  }
}
</script>

<style>
body{
  margin: 0;
  font-family: 'Nunito SemiBold';
}
</style>
