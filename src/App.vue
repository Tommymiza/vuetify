<template>
  <v-app>
    <navbar />
    <v-main class="grey darken-1">
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import navbar from './components/navbar.vue';

export default {
  components: { navbar },
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
body{
  &::-webkit-scrollbar{
    display: none;
  }
}
</style>