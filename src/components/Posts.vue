<template>
    <div id="app">
        <add-post @addNewPost="addPost($event)"/>
        <ul v-for="(post, index) in posts" :key="index">
           <Single-post :post='post' @deletePost="deletePost($event)"></Single-post>
        </ul>
    </div>
</template>

<script>
import SinglePost from './SinglePost'
import AddPost from './AddPost'
import { postService } from '../services/post-service'


export default {
    components: {
        SinglePost,
        AddPost
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
        },

        addPost (post) {
            let postId = this.posts.length + 1
            post.id = postId
            this.posts.unshift(post)
        }
    }
}
</script>

<style scoped>

</style>