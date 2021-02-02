<template>
  <v-sheet style="position: relative;">
    <v-app-bar
      app
      src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
    >
      <v-app-bar-nav-icon
        class="white--text"
        v-on:click="cajonDeNavegacion = !cajonDeNavegacion"
      />
      <v-img
        alt="Vuetify Logo"
        class="shrink mr-2"
        contain
        src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
        transition="scale-transition"
        width="40"
      />
      <v-toolbar-title class="white--text mr-2"
        >uetified tasks 😎</v-toolbar-title
      >
      <v-spacer />
      <v-btn class="success ma-2">Ingresar</v-btn>
      <v-btn class="error ma-2">Salir</v-btn>
    </v-app-bar>
    <v-navigation-drawer app temporary v-model="cajonDeNavegacion" absolute>
      <v-list-item>
        <v-list-item-avatar>
          <v-img src="../assets/logo.png" />
        </v-list-item-avatar>
        <v-list-item-content>
          <v-list-item-title>[Avatar]</v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-divider />
      <v-list dense>
        <v-list-item
          v-for="elemento in lista"
          v-bind:key="elemento.nombre"
          v-bind:to="{ name: elemento.enlace }"
        >
          <v-list-item-icon>
            <v-icon>{{ elemento.icono }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ elemento.nombre }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-sheet>
</template>

<script>
export default {
  data() {
    return {
      cajonDeNavegacion: false,
      lista: [
        { nombre: "Inicio", icono: "mdi-view-dashboard", enlace: "Home" },
        { nombre: "Cuadrícula", icono: "mdi-grid", enlace: "Cuadricula" },
        {
          nombre: "Botones",
          icono: "mdi-gesture-tap-button",
          enlace: "Botones"
        },
        { nombre: "Tarjetas", icono: "mdi-cards", enlace: "Tarjetas" },
        { nombre: "Acerca de", icono: "info", enlace: "About" }
      ]
    };
  }
};
</script>
