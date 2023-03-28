<script >
import axios from 'axios';
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
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
      .then((response) => {
        console.log(response);
        this.store.cards = response.data.data;
      }),
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
          console.log(response);
          this.store.archetypes = response.data;
        })
  }
}
</script>

<template>
  <Header />
  <Main />
</template>

<style lang="scss" scoped></style>
