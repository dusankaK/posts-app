<template>
    <div id="app">
        <ul v-for="(post, index) in posts" :key="index">
           <Single-post :post='post'></Single-post>
        </ul>
    </div>
</template>

<script>
import SinglePost from './SinglePost'

export default {
    components: {
        SinglePost
    },

    data() {
        return {
            posts: [{title: 'test', body: 'nenenen'}]
        }
    }
    
}
</script>

<style scoped>
</style>