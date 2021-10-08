<template>
  <v-card>
    <v-card-title primary-title> Usuarios </v-card-title>
    <v-card-text>Formulario para eliminar usuarios </v-card-text>
    <v-card-text>
      <v-form ref="form_users">
        <v-text-field
          name="id"
          label="Nro de Identificación"
          id="id"

        ></v-text-field>
        
        <v-btn
          
          color="error"
          
          
        >
         Eliminar usuario
        </v-btn>
        
      </v-form>
    </v-card-text>
   
    
  </v-card>
</template>