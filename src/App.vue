<template>
  <v-app>
    <NavbarWish/>

    <v-content>
        <transition name="scroll-y-reverse-transition" mode="out-in">
            <router-view></router-view>
        </transition>
      
    </v-content>
  </v-app>
</template>

<script>
import NavbarWish from './components/NavbarWish'

export default {
  name: 'App',
  components: {
    NavbarWish
  },
  data: () => ({}),
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Noto+Sans:400,700&display=swap');

body * {
    font-family: 'Noto Sans', sans-serif;

    ::-webkit-scrollbar {
        width: 8px;
    }
    
    ::-webkit-scrollbar-track {
        background: white;
    }
    
    ::-webkit-scrollbar-thumb {
        border-radius: 10px;
        background: #d4e3eb;
    }
}
</style>
