<template>
  <v-container>
    <SearchJokes v-on:search-text="SearchText" />
    <Joke
      v-for="joke in jokes"
      :key="joke.id"
      :joke="joke.joke"
      :id="joke.id"
    />
  </v-container>
</template>
<script>
import axios from "axios";
import Joke from "../../components/Joke";
import SearchJokes from "../../components/SearchJokes";

export default {
  components: {
    Joke,
    SearchJokes,
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
  methods: {
    async SearchText(text) {
      const config = {
        headers: {
          Accept: "application/json",
        },
      };
      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        );
        this.jokes = res.data.results;
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>