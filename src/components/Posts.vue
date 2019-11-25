<template>
    <div id="app">
        <ul v-for="(post, index) in posts" :key="index">
           <Single-post :post='post'></Single-post>
        </ul>
    </div>
</template>

<script>
import SinglePost from './SinglePost'
import { postService } from '../services/post-service'


export default {
    components: {
        SinglePost
    },

    data() {
        return {
            posts: []
        }
    },

    created () {
        postService.getPosts().then(response =>{
            this.posts = response.data;
      })
      
  },
    
}
</script>

<style scoped>
</style>