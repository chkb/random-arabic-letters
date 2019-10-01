<template>
  <v-app>
    <v-app-bar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>ARABISKE BOGSTAVER</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-content>
      <RandomArabicLetters/>
    </v-content>
  </v-app>
</template>

<script>
import RandomArabicLetters from './components/RandomArabicLetters';

export default {
  name: 'App',
  components: {
    RandomArabicLetters,
  },
  data: () => ({
    //
  }),
};
</script>
