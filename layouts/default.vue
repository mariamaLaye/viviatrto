<template>
<v-app dark>
  <v-main>
    
    
    <v-container > 
       <v-alert type="info" v-if="false" color="pink" max-width="600" >
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
 
      
  