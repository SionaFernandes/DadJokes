<template>
  <v-app >
    <v-main>
      <v-container>
        <AppHeader/>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import AppHeader from '../components/AppHeader';

export default {
  data () {
    return {
      fixed: false,
      title: 'Vuetify.js'
    }
  },
  components:{
    AppHeader
  }
}
</script>
