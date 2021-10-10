<template>
  <div class="container">
    <NuxtLink to="users">users</NuxtLink>
    <NuxtLink to="/">home</NuxtLink>
    <section class="articles">
      <div class="column is-8 is-offset-2">
        <div class="card article" v-for="(post,index) in posts">
          <div class="card-content">
            <div class="media">
              <div class="media-content has-text-centered">
                <p class="title article-title">{{ index + 1 }}-{{ post.title }}</p>
                <div class="tags has-addons level-item">
                    <span
                      class="tag is-rounded is-info">@{{ users.find(user => user.id === post.userId).username }}</span>
                  <span class="tag is-rounded">May 10, 2018</span>
                </div>
              </div>
            </div>
            <div class="content article-body">
              <p>{{ post.body }}</p>
            </div>
          </div>
        </div>
      </div>

    </section>
  </div>
</template>

<script>
export default {
  name: "posts",
  async asyncData(context) {
    const posts = await context.$axios.$get('/posts')
    const users = await context.$axios.$get('/users')
    return {posts, users}
  }
}
</script>

<style scoped>

</style>
