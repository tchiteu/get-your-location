<template>
  <v-app>
    <v-content>
      <Mapa/>
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

  data: () => ({
    //
  }),
};
</script>
