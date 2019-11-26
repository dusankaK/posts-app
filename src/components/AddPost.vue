<template>
    <div>
        <form @submit.prevent="addPost(newPost)" class="wrappForm">
            <div class="form-group">
                <label for="post-title">Post title</label>
                <input v-model="newPost.title" type="text" class="form-control">
            </div>
            <div class="form-group">
                <label for="post-body">Body</label>
                <input v-model="newPost.body" type="text" class="form-control">
            </div>
            <div class="form-group text-center">
            <button type="submit" class="btn btn-primary">Submit</button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            newPost: {}
        }
    },
    methods: {
        addPost (newPost) {
            this.$emit('addNewPost', newPost)
            this.newPost = {}
        }
    }
}
</script>

<style scoped>
    .wrappForm {
        width:60%;
        margin: 15px auto;
    }
</style>