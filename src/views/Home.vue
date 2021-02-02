<template>
  <v-container>
    <v-row>
      <!-- tareas -->
      <v-col sm="12" md="6">
        <v-card
          class="mb-3"
          v-for="(tarea, indice) in quehaceres"
          v-bind:key="tarea.codigo"
        >
          <v-card-title>
            <v-chip color="primary" label text-color="white">
              <v-icon left>
                mdi-label
              </v-icon>
              {{ tarea.titulo }}
            </v-chip>
          </v-card-title>
          <v-card-text>{{ tarea.descripcion }}</v-card-text>
          <v-card-actions>
            <v-btn color="warning" v-on:click="editar(indice)" class="ml-2"
              >Editar</v-btn
            >
            <v-btn color="error" @click="eliminar(tarea.codigo)"
              >Eliminar</v-btn
            >
          </v-card-actions>
        </v-card>
      </v-col>
      <!-- formulario -->
      <v-col sm="12" md="6">
        <v-card class="pa-2"
          ><v-form v-on:submit.prevent="agregar">
            <v-text-field label="Título de la tarea" v-model="titulo" />
            <v-textarea label="Descripción de la tarea" v-model="descripcion" />
            <v-btn
              v-if="typeof editando !== 'number'"
              block
              color="success"
              type="submit"
            >
              Agregar tarea
            </v-btn>
            <v-btn
              v-else
              block
              color="warning"
              @click.prevent="confirmarEdicion"
              >Editar tarea</v-btn
            >
          </v-form></v-card
        >
      </v-col>
    </v-row>
    <!-- barra de bocadillos -->
    <v-snackbar v-model="barraBeBocadillos">
      {{ mensajeDeBocadillo }}
      <template v-slot:action="{ attrs }">
        <v-btn
          color="accent"
          text
          v-bind="attrs"
          @click="barraBeBocadillos = false"
        >
          Cerrar
        </v-btn>
      </template>
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    quehaceres: [
      {
        codigo: 1,
        titulo: "Título de la tarea",
        descripcion: "Descripción de la tarea"
      }
    ],
    titulo: "",
    descripcion: "",
    barraBeBocadillos: false,
    mensajeDeBocadillo: "",
    editando: false
  }),
  methods: {
    agregar() {
      // console.log(this.titulo, this.descripcion);
      if (this.titulo.trim() === "" || this.descripcion.trim() === "") {
        this.mensajeDeBocadillo = "¡Complete todos los campos 😝!";
        this.barraBeBocadillos = true;
      } else {
        this.quehaceres.push({
          codigo: Date.now(),
          titulo: this.titulo,
          descripcion: this.descripcion
        });
        this.titulo = "";
        this.descripcion = "";
        this.barraBeBocadillos = true;
        this.mensajeDeBocadillo = "¡Tarea ingresada correctamente 👍!";
      }
    },
    eliminar(codigo) {
      this.quehaceres = this.quehaceres.filter(
        tarea => tarea.codigo !== codigo
      );
      this.editando = false;
    },
    editar(indice) {
      this.editando = indice;
      this.titulo = this.quehaceres[indice].titulo;
      this.descripcion = this.quehaceres[indice].descripcion;
    },
    confirmarEdicion() {
      if (this.titulo.trim() === "" || this.descripcion.trim() === "") {
        this.mensajeDeBocadillo = "¡Complete todos los campos 😝!";
        this.barraBeBocadillos = true;
      } else {
        this.quehaceres[this.editando].titulo = this.titulo;
        this.quehaceres[this.editando].descripcion = this.descripcion;
        this.mensajeDeBocadillo = "¡Tarea correctamente editada 😎!";
        this.barraBeBocadillos = true;
      }
      this.editando = false;
      this.titulo = "";
      this.descripcion = "";
    }
  }
};
</script>
