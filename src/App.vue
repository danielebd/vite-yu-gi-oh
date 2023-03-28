<script >

import { store } from './store';
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
    return {
      store
    }

  },
  
}
</script>

<template>
  <Header />
  <Main />
</template>

<style lang="scss" scoped></style>
