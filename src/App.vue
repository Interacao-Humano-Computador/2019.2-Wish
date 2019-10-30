<template>
  <v-app>
    <NavbarWish/>

    <v-content>
      <HelloWorld/>
    </v-content>
  </v-app>
</template>

<script>
import NavbarWish from './components/NavbarWish'
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',
  components: {
    HelloWorld,
    NavbarWish
  },
  data: () => ({
    //
  }),
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Noto+Sans:400,700&display=swap');

body * {
    font-family: 'Noto Sans', sans-serif;
}
</style>
