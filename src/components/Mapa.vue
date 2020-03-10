<template>
  <v-container>
    <v-row>
      <v-col md12>
        <iframe class="mapa" frameborder="0" scrolling="no" src="https://www.openstreetmap.org/export/embed.html?bbox=-69.1692352294922%2C-19.047839415523125%2C-68.78608703613283%2C-18.849111862024&amp;layer=mapnik" style="border: 1px solid black"></iframe>
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
