<template>
  <form @submit.prevent="onSubmit">
     <v-text-field
      label="Search Jokes.."
      type="text" placeholder="Search Jokes.."
      hide-details="auto"
      v-model="text" 
    ></v-text-field>
    <v-btn type="submit" class="mt-4">
      Search Joke
    </v-btn>
  </form>
</template>
<script>
export default {
  name: "SearchJokes",
  data() {
    return {
      text: "",
    };
  },
  methods: {
    onSubmit() {
      this.$emit("search-text", this.text);
      this.text = "";
    },
  },
};
</script>
<style>
</style>