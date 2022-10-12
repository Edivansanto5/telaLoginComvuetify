<template>
<div>
  <registrationForm/>
 
</div>

</template>

<script>
  import HelloWorld from '../components/HelloWorld'
  import RegistrationForm from '../components/RegistrationForm.vue'

  export default {
    name: 'Home',

    components: {
      HelloWorld,
        RegistrationForm,
    
    },
  }
</script>
