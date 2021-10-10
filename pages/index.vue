<template>
  <div class="container">
    <div>
      <NuxtLink to="/posts">پست ها</NuxtLink>
      <NuxtLink to="/users">کاربران</NuxtLink>
      <p>counter:{{ $store.state.counter.counter }}</p>
      <button @click="$store.dispatch('counter/increment')">افزایش</button>
      <button @click="$store.dispatch('counter/decrement')">کاهش</button>
    </div>
    <!--   <img :src="require('~/assets/download.png')" alt="">-->
  </div>
</template>

<script>
export default {}
</script>
