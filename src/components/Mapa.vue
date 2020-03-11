<template>
  <iframe :height="alturaTela" class="mapa" :src="`https://www.openstreetmap.org/export/embed.html?bbox=${long},${lat},${long},${lat}&amp;layer=mapnik&amp;marker=${lat},${long}`"></iframe>
</template>

<script>
  export default {
    name: 'Mapa',
    
    props: {
      lat: Number,
      long: Number,
    },
    computed: {
      alturaTela() {
        return window.screen.height
      }
    }
  }
</script>

<style>
  .mapa {
    width: 100%;
    border: none;
  }
</style>
