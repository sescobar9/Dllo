<template>
  <v-card>
    <v-card-title primary-title> Usuarios </v-card-title>
    <v-card-text>Formulario para Actualizar usuarios </v-card-text>
    <v-card-text>
      <v-form ref="form_users">
        <v-text-field
          name="id"
          label="Nro de Identificación"
          id="id"
          v-model="usuario.id"
          :disabled="is_updating"
          :rules="requiredRule"
        ></v-text-field>
        <v-row>
          <v-col sm="12" md="6">
            <v-text-field
              name="nombre"
              label="Nombre"
              id="nombre"
              v-model="usuario.nombre"
              :rules="requiredRule"
            ></v-text-field>
          </v-col>
          <v-col sm="12" md="6">
            <v-text-field
              name="apellidos"
              label="Apellidos"
              id="apellidos"
              v-model="usuario.apellidos"
              :rules="requiredRule"
            ></v-text-field>
          </v-col>
        </v-row>
        <v-row v-if="!is_updating">
          <v-col cols="6">
            <v-text-field
              :type="show_password ? 'text' : 'password'"
              name="clave"
              label="Contraseña"
              id="clave"
              v-model="usuario.clave"
              :rules="requiredRule"
              :append-icon="show_password ? 'mdi-eye-off' : 'mdi-eye'"
              @click:append="show_password = !show_password"
            ></v-text-field>
          </v-col>
          <v-col cols="6">
            <v-text-field
              :type="show_repeat_password ? 'text' : 'password'"
              name="clave"
              label="Repetir Contraseña"
              id="repetir_clave"
              v-model="usuario.repetir_clave"
              :rules="repetPassword"
              :append-icon="show_repeat_password ? 'mdi-eye-off' : 'mdi-eye'"
              @click:append="show_repeat_password = !show_repeat_password"
            >
            </v-text-field>
          </v-col>
        </v-row>
        <br />
        <v-select
          :items="roles"
          v-model="usuario.rol"
          label="Rol"
          item-text="nombre"
          item-value="id"
          :rules="requiredRule"
        ></v-select>

        <br />
        <!-- <v-select :items="roles" label="Rol" item-text="nombre" id="rol" item-value="id"></v-select> -->
        <v-btn
          
          color="primary"
          
          
        >
          Actualizar usuario
        </v-btn>
        
      </v-form>
    </v-card-text>
   
    
  </v-card>
</template>
<script>

export default {
  data() {
    return {
      usuario: {},
      roles: [
        { id: 2, nombre: "Profesor" },
        { id: 1, nombre: "Estudiante" },
      ],
      
      users: [],
      is_updating: false,
      requiredRule: [(v) => !!v || "El campo es obligatorio"],
      repetPassword: [
        (v) => !!v || "El campo es obligatorio",
        (v) => v === this.usuario.clave || "Las contraseñas no coinciden",
      ],
      show_password: false,
      show_repeat_password: false,
      loading: false,
    };
  },
  


};
</script>