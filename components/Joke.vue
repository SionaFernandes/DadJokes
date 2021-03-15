<template>
  <v-card elevation="2" shaped class="pa-4 my-4">
    <NuxtLink :to="'jokes/' + id" class="text-decoration-none">
      <div class="joke">
        <p>{{ joke }}</p>
      </div>
    </NuxtLink>
  </v-card>
</template>
<script>
export default {
  name: "Joke",
  props: ["joke", "id"],
};
</script>
<style>
a{
  color: #000;
}
</style>