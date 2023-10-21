<script lang="ts" setup></script>

<template>
  <div>
    <nav class="navbar navbar-expand-lg bg-dark" data-bs-theme="dark">
      <div class="container">
        <NuxtLink class="navbar-brand" to="/">HOME</NuxtLink>
        <button aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation"
                class="navbar-toggler" data-bs-target="#navbarSupportedContent" data-bs-toggle="collapse"
                type="button">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div id="navbarSupportedContent" class="collapse navbar-collapse">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <NuxtLink aria-current="page" class="nav-link active" to="/posts">POSTS</NuxtLink>
            </li>
          </ul>
          <ul class="navbar-nav ms-auto mb-2 mb-lg-0" role="search">
            <a class="btn btn-success" href="https://santrikoding.com" target="_blank">SANTRIKODING.COM</a>
          </ul>
        </div>
      </div>
    </nav>

    <!--- render page -->
    <slot/>
  </div>
</template>

<style scoped>
body {
  background-color: lightgray;
  font-family: 'Quicksand', sans-serif
}
</style>
