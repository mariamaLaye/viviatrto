<template>
  <v-main>
    
   
      <v-card v-if="form"
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
            label="Title"
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
      @click="remove"
      
      > 
      <v-icon left>
      {{ icons.mdiDelete }}
      </v-icon>
      Delete
    </v-btn>
      </v-col>
    </v-row>
  </v-container>
  </v-card>
</v-main>
</template>

<script>

import { Vue, Component, Prop } from 'vue-property-decorator'

/*export default class  extends Vue {
@Prop({ model: '' })  propB
@Prop({ description: '' })  propC
@Prop({ form: true })  propD
@Prop({ icons: mdiDelete })  propE


}*/
import {
    mdiDelete,
  } from '@mdi/js'

  export default {

    data: () => ({
      name:'saisie',
      model: '',
      description:'',
      form:true,
    
      icons: {
         mdiDelete,
      
      },
      
    }),

    methods:{

      remove( ){
          
        this.form=false
        
      
      },
       store() {
   
         localStorage.setItem("model",this.input)
       
      
      
    
       }
    }
  }
  
</script>