<template>
<v-app dark>
  <v-main>
    <v-container>
      <div class="text-center">
            <v-btn to="Add"
             
              rounded
              color="primary"
              dark
               >   + ADD NEW TODO :)
            </v-btn>
      </div>
    </v-container>
    
    <v-container > 
       <v-alert type="info" color="pink" max-width="600" >
          Aucun TODO enregistré !!!
       </v-alert>
    </v-container>
     <Nuxt />
  </v-main>
</v-app>
 </template>

 <script>

    export default{
      data:() =>
      ({
        
      

      }),

      methods:{

        open(){
        
       
        

        }
        
      }
    }

 </script>
 
      
  