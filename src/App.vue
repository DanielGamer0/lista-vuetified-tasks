<template>
  <v-app>
    <barra-de-herramientas />
    <v-main>
      <router-view />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";
import BarraDeHerramientas from "@/components/BarraDeHerramientas.vue";

export default Vue.extend({
  components: {
    BarraDeHerramientas
  }
});
</script>
