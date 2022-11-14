<template>
  <AppHeader title="The Breaking Bad API" />
  <main>
    <CharacterList :characters="characterList" />
  </main>
</template>

<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CharacterList from './components/CharacterList.vue';
export default {
  components: {
    AppHeader,
    CharacterList
  },
  data() {
    return {
      apiURL: 'https://www.breakingbadapi.com/api/characters',
      characterList: [],

    }
  },
  methods: {
    getCharacters() {
      axios.get(this.apiURL).then(
        (res) => {
          this.characterList = [...res.data];
          console.log(this.characterList)

        }
      ).catch((error) => {
        console.log(error);
      })
    }
  },
  created() {
    this.getCharacters()
  }
}
</script>

<style lang="scss" scoped>

</style>