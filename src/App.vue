<template>
  <AppHeader title="The Breaking Bad API" />
  <main>
    <SearchComponent @filteredChar="getCharacters" />
    <CharacterList />
  </main>
</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharacterList from './components/CharacterList.vue';
import SearchComponent from './components/SearchComponent.vue';
import { store } from "./store";

export default {
  components: {
    AppHeader,
    CharacterList,
    SearchComponent
  },
  data() {
    return {
      store,
      endAPI: "characters"
    }
  },
  methods: {
    getCharacters() {
      let options = null;
      if (store.search.category) {
        options = {
          params: {
            category: store.search.category,
          },
        };
      }
      const charApiURL = store.apiURL + this.endAPI;
      axios.get(charApiURL, options).then((res) => {
        store.characterList = [...res.data];
      });
    },
  },
  created() {
    this.getCharacters();
  },
}
</script>

<style lang="scss" scoped>

</style>