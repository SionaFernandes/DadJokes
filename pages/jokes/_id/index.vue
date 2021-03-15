<template>
  <div>
    <NuxtLink to="/jokes">Go back to Jokes </NuxtLink>

    <v-card elevation="2" shaped class="pa-4 my-4">
      <h3>{{ joke }}</h3>
      <small>Joke ID: {{ $route.params.id }}</small>
    </v-card>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: {},
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );
      this.joke = res.data.joke;
    } catch (error) {
      console.log(error);
    }
  },
};
</script>