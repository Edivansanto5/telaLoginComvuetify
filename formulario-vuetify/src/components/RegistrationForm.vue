<template>
  <v-container fluid class="fluid">
      <v-row justify="center" align="center" class="row">

         <v-col cols="6" sm="12" md="6" xs="12" class="text-center purple darken-2"
         style="height: 100vh">

            <v-row justify="center" align="center" style="height: 80vh">
               <v-col>
                  <h1 class="white--text">LogRockets</h1>
               </v-col>
            </v-row>

         </v-col>

         <v-col cols="6" sm="12" md="6" xs="12" class="text-center" style="height: 100vh">
            <h1>Welcome to LogRockets</h1>
            <p>Please complete this form to create an account</p>

            <v-form ref="form" class="mx-2" lazy-validation>
                <v-row>
                  <v-col cols="6">
                     <v-text-field v-model="firstname" :rules="nameRules" label="Primeiro Nome"></v-text-field>
                  </v-col>

                  <v-col cols="6">
                     <v-text-field v-model="lastname" :rules="nameRules" label="Segundo Nome"></v-text-field>
                  </v-col>

                  <v-row>
                     <v-col cols="12">
                        <v-text-field v-model="email" :rules="emailRules" label="Email" required />
                     </v-col>
                  </v-row>

               </v-row> 
            </v-form>
            
         </v-col>
         
         
      </v-row>
    
  </v-container>
</template>


<script>
      export default{
         data(){
            return{
               firstname: '',
               lastname: '',
               nameRules: [v => !!v || 'O nome é obrigatório',v => (v && v.length <= 10) ||
                'O nome deve ter menos de 10 caracteres',],
            }
         }
      }
</script>