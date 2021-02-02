<template>
  <v-container fluid>
    <v-row dense>
      <v-col
        v-for="tarjeta in tarjetas"
        :key="tarjeta.titulo"
        lg="4"
        md="6"
        sm="12"
        xl="3"
      >
        <v-card>
          <v-img class="white--text align-end" v-bind:src="tarjeta.fuente">
            <v-card-title v-text="tarjeta.titulo" />
          </v-img>
          <v-card-text>{{ texto }}</v-card-text>
          <v-card-actions>
            <v-btn color="info" text @click="dialogo = true">Acción</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <!--Dialogs-->
    <v-dialog v-model="dialogo" persistent width="500">
      <v-card>
        <v-card-title
          >Dialog de <v-icon>mdi-vuetify</v-icon>uetify</v-card-title
        >
        <v-card-text>{{ texto }}</v-card-text>
        <v-divider />
        <v-card-actions>
          <v-btn v-on:click="dialogo = false">Cerrar</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!--Fin Dialog-->
  </v-container>
</template>

<script>
export default {
  data: () => ({
    tarjetas: [
      {
        titulo: "Cafe Badilico",
        fuente: "https://cdn.vuetifyjs.com/images/cards/cooking.png"
      },
      {
        titulo: "Pre-fab homes",
        fuente: "https://cdn.vuetifyjs.com/images/cards/house.jpg"
      },
      {
        titulo: "Favorite road trips",
        fuente: "https://cdn.vuetifyjs.com/images/cards/road.jpg"
      },
      {
        titulo: "Best airlines",
        fuente: "https://cdn.vuetifyjs.com/images/cards/plane.jpg"
      }
    ],
    texto:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum finibus suscipit sollicitudin. Quisque lacus lectus, sagittis eget tempus et, lobortis non libero. Aenean nec metus non nulla semper convallis et ullamcorper nunc. Mauris sem erat, placerat et gravida in, consectetur sed dui. Aenean sagittis velit at sollicitudin eleifend. Praesent vel viverra diam. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras dictum augue vel vulputate posuere. Nulla at risus sed leo lobortis egestas. Quisque ullamcorper risus scelerisque efficitur hendrerit.",
    dialogo: false
  })
};
</script>
