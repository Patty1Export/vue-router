<template>
  <div id="single-blog">
      <h1>{{ blog.title }}</h1>
      <article>{{ blog.content }}</article>
      <p>Author: {{ blog.author }}</p>
      <ul>
        <li v-for="category in blog.categories">{{ category }}</li>
      </ul>
      </div>
  </div>
</template>

<script>
// Imports
import searchMixin from '../mixins/searchMixin';
export default {
  data () {
      return {
          id: this.$route.params.id,
          blog: {}
      }
  },
  created() {
      this.$http.get('https://vue-playlist-b9178-default-rtdb.firebaseio.com/posts/' + this.id + '.json').then(function(data){
          // console.log(data);
          return data.json();
      }).then(function(data){
        this.blog = data;
      })
  }
}
</script>

<style>
#single-blog{
  max-width: 960px;
  margin: 0 auto;
}
</style>
