<template>
   <v-card
    class="mx-auto"
    max-width="600"
    max-height="800"
    color="green"
    outlined
  >
      <v-container>
        <v-row
             justify="space-between"
        >
        <v-col
            cols="12"
            md="4"
        >
         <v-form ref="form">
            <v-text-field
            v-model="model"
            :counter="max"
            :rules="rules"
            label="title"
        ></v-text-field>
        </v-form>
      </v-col>
      <v-col
        cols="12"
        md="6"
      >
      <v-container fluid>
        <v-textarea
         counter
        label="description"
        :rules="rules"
        :value="value"
       ></v-textarea>
  </v-container>
  <v-btn align right
      color="error"
      class="mr-4"
      @click="reset"
      
      > 
      <v-icon left>
      {{ icons.mdiDelete }}
      </v-icon>
      {{boutton}}
    </v-btn>
      </v-col>
    </v-row>
  </v-container>
  </v-card>
</template>



<script>
import {
    mdiDelete,
  } from '@mdi/js'

  export default {
    name:'saisie',
    props:['boutton'],
  }
  
  
</script>