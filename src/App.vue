<template>
  <v-app>
    <v-content>
      <Mapa :lat="latitude" :long="longitude">
      </Mapa>
    </v-content>
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
  }),
  methods: {
    getPosition(position) {
      this.latitude = position.coords.latitude
      this.longitude = position.coords.longitude
    }
  }
};
</script>
