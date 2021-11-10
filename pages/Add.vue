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
      <v-card 
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
            label="Title"
            ref="titre"
            :v-model="titre"
            :value="value"
          ></v-text-field>
         
        </v-form>
      </v-col>
    <v-col
        cols="12"
        md="6"
      >
      <v-container fluid>
        <v-textarea
        :value="value"
         label="description"
        
          ></v-textarea>
      </v-container>
      <div>
          <v-btn align right 
            color="error"
            class="mr-4"
            @click="remove()"> 
            <v-icon left>
             {{ icons.mdiDelete }}
           </v-icon>
             Delete
          </v-btn>
         <br>
         <p>{{date()}}</p>
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
   
    var TODO =[]
    import { Vue, Component, Prop,Emit } from 'vue-property-decorator'
    import moment from 'moment'
    import {mdiDelete,} from '@mdi/js'

    export default {

    data: () => ({
      titre:null,
       Title:'',
      description:'',
       TodoItem:[],
       value:'',
      alert:false,
        icons: {
         mdiDelete,
      },
    
    }),
    
    
     //Réafficher le localstorage

      created(){
        
        this.TodoItem=JSON.parse(localStorage.getItem(TODO)|| '[]')
    },

  //les Methodes
    methods:{
      
 //creer la date
      date(){
        var date
           return moment(date).format('MMMM Do YYYY, h:mm:ss a')
      },

  //supprimer les TODOS
      remove(){
        var item
        this.TodoItem.splice(item,1)
        localStorage.getItem(this.TodoItem)
        localStorage.removeItem(this.TodoItem)

        if(localStorage.length ==0)
             this.alert= true
        },
        
     
  //Ajouter un TODO
      ajouItem()
      {
        this.TodoItem.push({
         titre:'',
        description:this.value,  
             
        })
           localStorage.setItem(TODO,JSON.stringify(this.TodoItem))
            this.alert= false
            
      },

    },

   
  }
  
</script>

