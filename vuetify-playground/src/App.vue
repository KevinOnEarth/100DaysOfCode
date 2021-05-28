<template>
  <v-app>
    <ChartComponent />
  </v-app>
</template>

<script>
import ChartComponent from './components/ChartComponent';

export default {
  name: 'App',

  components: {
    ChartComponent,
  },

  data: () => ({
    //
  }),
};
</script>
