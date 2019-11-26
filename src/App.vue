<template>
  <div id="app">
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
      <div class="container">
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto">
            <router-link tag="li" class="nav-item" to="/posts" active-class="active">
              <a class="nav-link">Posts</a>
            </router-link>
          </ul>
        </div>
      </div>
    </nav>
   <router-view/>
  </div>
</template>

<script>

export default {
  
}
</script>

<style>
</style>
