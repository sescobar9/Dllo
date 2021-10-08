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
        <br/>
            
            <v-select
            :items="salas"
            label= "salas disponibles"
            item-text= "salas"
            item-value= "id"
            ></v-select>
            
        <br/>
        <br/>
            <v-select
            :items="horas"
            label= "horas disponibles"
            item-text="horas"
            item-value="id"
            ></v-select>
        <br/>

        <v-btn
          :loading="loading"
          color="success"
          v-if="!is_updating"
        >
          Crear Reserva
        </v-btn>

    </v-card-text>
    </v-card>
</template>
<script>
import config from "../assets/js/config";

export default {
    data() {
        return {
            horas:[
                {id:1, horas:"6:00-8:00"},
                {id:2, horas:"8:00-10:00"},
                {id:3, horas:"10:00-12:00"},
                {id:4, horas:"12:00-14:00"},
                {id:5, horas:"14:00-16:00"},
            ],
            salas:[
                {id:1, salas:"sala1"},
                {id:2, salas:"sala2"},
                {id:3, salas:"sala3"},
                {id:4, salas:"sala4"},
            ]  
            
        }
    },
}

</script>
