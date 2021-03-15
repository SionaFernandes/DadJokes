<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div class="text-center pa-6">
        <h1>Welcome to the jokes Page</h1>
      </div>
    </v-col>
  </v-row>
</template>

<script>

export default {
  head() {
    return {
      title: "Dad Jokes for all",
      meta: [
        {
          hid: "description",
          name: "description",
          content: "Corny jokes",
        },
      ],
    };
  },
};
</script>
