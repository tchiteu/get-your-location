<template>
  <v-container>
    <v-row>
      <v-col md12>
        <iframe class="mapa" :src="`https://www.openstreetmap.org/export/embed.html?bbox=${long},${lat},${long},${lat}&amp;layer=mapnik&amp;marker=${lat},${long}`"></iframe>
      </v-col>      
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Mapa',
    
    props: {
      lat: Number,
      long: Number,
    },
    data: () => ({
      
    }),
  }
</script>

<style>
  .mapa {
    width: 100%;
    min-height: 400px;
  }
</style>
