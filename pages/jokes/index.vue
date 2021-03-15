<template>
  <div>
    <v-container>
      <Joke
        v-for="joke in jokes"
        :key="joke.id"
        :joke="joke.joke"
        :id="joke.id"
      />
    </v-container>
  </div>
</template>
<script>
import axios from "axios";
import Joke from "../../components/Joke";

export default {
  components: {
    Joke,
  },
  head() {
    return {
      title: "Jokes List",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "jokes",
        },
      ],
    };
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json",
      },
    };
    try {
      const res = await axios.get("https://icanhazdadjoke.com/search", config);
      this.jokes = res.data.results;
    } catch (error) {
      console.log(error);
    }
  },
  data() {
    return {
      jokes: [],
    };
  },
};
</script>