<template>
  <v-container>
    <v-row justify="space-around" align="center">
      <v-col>
        <v-btn>Botón</v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary">ColorPrimary</v-btn>
      </v-col>
      <v-col>
        <v-btn color="blue" dark>DarkBlue</v-btn>
      </v-col>
      <v-col>
        <v-btn color="secondary" text>Sin fondo</v-btn>
      </v-col>
      <v-col>
        <v-btn color="warning" large>Grande</v-btn>
      </v-col>
      <v-col>
        <v-btn color="warning" small>Pequeño</v-btn>
      </v-col>
      <v-col>
        <v-btn color="warning" :disabled="true">Deshabilitado</v-btn>
      </v-col>
      <v-col>
        <v-btn color="info" depressed>Sin sombreado</v-btn>
      </v-col>

      <v-col>
        <v-btn>
          <v-icon>mdi-heart</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary">
          <v-icon>favorite</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary" icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary" text>
          <v-icon>favorite</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary" fab large>
          <v-icon>favorite</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="primary" fab small>
          <v-icon>mdi-heart</v-icon>
        </v-btn>
      </v-col>

      <v-col>
        <v-btn color="success">
          Texto
          <v-icon>forum</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="success">
          Texto
          <v-icon class="ml-2">forum</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="success">
          Texto
          <v-icon right>forum</v-icon>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn color="success" outlined block>
          <v-icon left>forum</v-icon>Texto
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>
