<template>
  <header class="header d-flex justify-space-between">
    <h1>Header</h1>
    <ul class="d-flex justify-space-between">
      <li class="mx-10"><NuxtLink to="/"> Go to Home </NuxtLink></li>
      <li class="mx-10"><NuxtLink to="/jokes"> Go to Jokes </NuxtLink></li>
    </ul>
  </header>
</template>
<script>
export default {
    name:"AppHeader"
}
</script>