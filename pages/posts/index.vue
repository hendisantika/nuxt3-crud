<script lang="ts" setup>
//meta title
useHead({
  title: 'Data Posts - hendisantika.com',
});

//init config
const config = useRuntimeConfig();

//fetch data from API with "useAsyncData"
const {data: posts}: any = await useAsyncData('posts', () => $fetch(`${config.public.apiBase}/api/posts`))

</script>

<template>
  <div class="container mt-5 mb-5">
    <div class="row">
      <div class="col-md-12">
        <NuxtLink class="btn btn-md btn-success rounded shadow border-0 mb-3" to="/posts/create">ADD NEW POST</NuxtLink>
        <div class="card border-0 rounded shadow">
          <div class="card-body">
            <table class="table table-bordered">
              <thead class="bg-dark text-white">
              <tr>
                <th scope="col">Image</th>
                <th scope="col">Title</th>
                <th scope="col">Content</th>
                <th scope="col" style="width:15%">Actions</th>
              </tr>
              </thead>
              <tbody>
              <tr v-for="(post, index) in posts.data.data" :key="index">
                <td class="text-center">
                  <img :src="post.image" class="rounded-3" width="200"/>
                </td>
                <td>{{ post.title }}</td>
                <td>{{ post.content }}</td>
                <td class="text-center">
                  <NuxtLink :to="`/posts/edit/${post.id}`"
                            class="btn btn-sm btn-primary rounded-sm shadow border-0 me-2">EDIT
                  </NuxtLink>
                  <button class="btn btn-sm btn-danger rounded-sm shadow border-0">DELETE</button>
                </td>
              </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
