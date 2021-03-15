<template>
  <div>
    <v-container> Jokes </v-container>
  </div>
</template>
<script>
import axios from "axios";

export default {
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
      console.log(res.data);
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