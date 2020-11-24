<template>
 <v-app>
  <v-app-bar app class="teal darken-4" dark >
     <v-toolbar-title>
       Vuetify Dashboard
     </v-toolbar-title>
     <v-spacer />
     <v-btn 
      v-for="link in links"
      :key="`${link.label}-header-link`"
      text 
      rounded 
      :to="link.url"
    >
     {{link.label}}
    </v-btn>
     
   </v-app-bar>
  <v-content >
    <!-- login module -->
    <router-view></router-view>
  </v-content>
  <!-- footer -->
  <v-footer
    color="teal darken-2"
    padless
  >
    <v-row
      justify="center"
      no-gutters
    >
      <v-btn
        v-for="link in links"
        :key="`${link.label}-footer-link`"
        color="white"
        text
        rounded
        class="my-2"
        :to="link.url"
      >
        {{ link.label }}
      </v-btn>
      <v-col
        class="teal darken-4 py-4 text-center white--text"
        cols="12"
      >
        {{ new Date().getFullYear() }} — <strong>Vuetify Dashboard</strong>
      </v-col>
    </v-row>
  </v-footer>

 </v-app>
</template>

<script>


export default {
  name: 'App',
  components: {
    
  },
  data: () => ({
    
    links: [
        {
          label: 'Home',
          url: '/'
        },
        {
          label: 'Login',
          url: '/login'
        }
      ]
  }),
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
</style>
