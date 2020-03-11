<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" app clipped>
     <v-list-item class="mt-4" link>
        <v-list-item-action>
          <v-icon color="grey darken-1">mdi-plus-circle-outline</v-icon>
        </v-list-item-action>
        <v-list-item-title class="grey--text text--darken-1">Adicionar Amigos</v-list-item-title>
      </v-list-item>
    </v-navigation-drawer>

    <v-app-bar
      app
      clipped-left
      color="primary"
      dense
    >
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-icon class="mx-4">fab fa-marker</v-icon>
      <v-toolbar-title class="mr-12 align-center">
        <span class="title">Get Your Location</span>
      </v-toolbar-title>
    </v-app-bar>

    <v-row class="mt-9">
      <v-col md12>
        <Mapa :lat="latitude" :long="longitude"/>
      </v-col>
    </v-row>
  </v-app>
</template>

<script>
import Mapa from './components/Mapa.vue';

export default {
  name: 'App',

  components: {
    Mapa,
  },
  mounted() {
    if(navigator.geolocation) navigator.geolocation.getCurrentPosition(this.getPosition)
  },
  data: () => ({
    latitude: null,
    longitude: null,
    drawer: false,
  }),
  methods: {
    getPosition(position) {
      this.latitude = position.coords.latitude
      this.longitude = position.coords.longitude
    }
  }
};
</script>
