<template>
  <div>
    <h1>Questionnaire</h1>
    
    <p>{{ person.name }} </p>
  </div>
</template>

<script>
  import { ref } from 'vue';
  export default {
    name: 'Questionnaire',
    setup() {
      const person = ref({});
      console.log('setup')
      person.value = {
        name:'Your name here'
      }
      return {
        person
      }
    },
    mounted() {
      console.log('New component mounted.')
    }
  }
</script>

<style scoped>
</style>
