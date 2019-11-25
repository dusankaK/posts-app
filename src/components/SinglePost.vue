<template>
    <div class="container">
        <div class="card mb-3" style="width: 18rem;">
            <div class="card-body">
                <h5 class="card-title">{{ post.title }}</h5>
                <h6 class="card-subtitle mb-2 text-muted">{{ post.body }}</h6>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
    props: ['post']
  
}
</script>

<style scoped>
</style>