<template>
    <v-card>
        <v-card-title primary-title>Reservas</v-card-title>
        <v-card-text>Formulario para las Reservas</v-card-text>
    <v-card-text>
        <v-form ref="form_users">
            <v-text-field
            name = "id"
            label="codigo reserva"
            id="id"
            ></v-text-field>
        </v-form>
        <v-btn
          :loading="loading"
          color="error"
          v-if="!is_updating"
        >
          Eliminar Reserva
        </v-btn>

    </v-card-text>
    </v-card>
</template>
