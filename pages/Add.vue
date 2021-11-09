<template>
<v-responsive>
  <v-main>
    <v-container>
      <div class="text-center" >
          <v-btn 
             @click="ajouItem()"
              rounded
              color="primary"
              dark
               >   + ADD NEW TODO :)
            </v-btn>
      </div >
      <v-container > 
       <v-alert type="info" v v-if="alert" color="pink" max-width="600" >
          Aucun TODO enregistré !!!
       </v-alert>
    </v-container>
    </v-container>

      <div  v-for=" items in TodoItem"  v-bind:key="items.id">
       <br>
      <v-card v-show="form"
        class="mx-auto"
        max-width="600"
        max-height="500"
        color="green"
        outlined
        
     >
      
      <v-container >
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
  <div>
  <v-btn align right 
      color="error"
      class="mr-4"
      @click="remove(item)"
      
      > 
      <v-icon left>
      {{ icons.mdiDelete }}
      </v-icon>
      Delete
    </v-btn>
    
  </div>
      </v-col>
    </v-row>

  </v-container>
   
</v-card>
 
 </div>
</v-main>
</v-responsive>
</template>

<script>

import { Vue, Component, Prop } from 'vue-property-decorator'
import moment from 'moment'
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
     
      model: '',
      description:'',
      form:true,
       TodoItem:[],
       alert:true,
       date:'',
       
      icons: {
         mdiDelete,
      },
      
    }),

    methods:{

      remove(item){
          
       this.TodoItem.splice(item,1)
         
      
      },
      

      ajouItem()
      {
        this.TodoItem.push({
            model: "",
            description: "",
            date: moment().format("MMMM Do YYYY, h:mm:ss a"),
           
            
        })
         //localStorage.setItem("TodoItem", JSON.stringify(this.TodoItem)),
         this.form=true
         this.alert= false
        
      },
      store() {
   
       
         

        
       
       
      },

    }
  }
  
</script>
