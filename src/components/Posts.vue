<template>
    <div id="app">
        <ul v-for="(post, index) in posts" :key="index">
           <Single-post :post='post' @deletePost="deletePost($event)"></Single-post>
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
    methods: {
        deletePost (post) {
            let indexPost = this.posts.indexOf(post)
            this.posts.splice(indexPost, 1)
        }
    }
    
}
</script>

<style scoped>
</style>