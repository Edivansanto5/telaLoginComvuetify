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
            <v-row>
               <v-col cols="6">
                        <v-text-field v-model="password" type="password" :rules="passwordRules"
                           label="Password" required></v-text-field>
                        </v-col>
                     </v-row>
<!-- 
                  <v-checkbox v-model="firstcheckbox" :rules="[v => !!v || 'You must agree to continue!']"
                     label="I agree with Terms and Conditions" required>
                  </v-checkbox>

                  <v-checkbox v-model="seccheckbox" :rules="[v => !!v || 'You must agree to receive!']"
                     label="I want to receive LogRocket Emails" required>
                  </v-checkbox> -->

            
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
               nameRules: [v => !!v || 'O nome é obrigatório',v => (v && v.length <= 12) ||
                'O nome deve ter menos de 12 caracteres',],

               email: '',
               emailRules: [v => !!v || 'E-mail is Obrigatório',
               v => /^(([^<>()[\]\\.,;:\s@']+(\.[^<>()\\[\]\\.,;:\s@']+)*)|('.+'))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(v) || 'E-mail invalido',],

               password: '',
               passwordRules: [v => !!v || 'Password is required',
               v => /(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{6,}/.test(v) || 'Password must contain at least lowercase letter, one number, a special character and one uppercase letter',],
               firstcheckbox: false,
            }
         }
      }
</script>