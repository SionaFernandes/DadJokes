<template>
  <header class="header d-flex justify-space-between">
    <h1>Header</h1>
    <ul class="d-flex justify-space-between align-center">
      <li class="ml-10">
        <NuxtLink to="/"> Home </NuxtLink>
      </li>
      <li class="ml-10"><NuxtLink to="/jokes"> Jokes </NuxtLink></li>
    </ul>
  </header>
</template>
<script>
export default {
  name: "AppHeader",
};
</script>
<style>
ul {
  list-style: none;
}
</style>