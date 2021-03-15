<template>
  <div class="joke">
    <p>{{ joke }}</p>
  </div>
</template>
<script>
export default {
  name: "Joke",
  props: ["joke", "id"],
};
</script>
<style>
.joke{
    border: 1px dotted #ccc;
    padding: 1rem;
    margin: 1rem 0 ;
}
</style>