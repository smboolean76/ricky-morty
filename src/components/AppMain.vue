<script>
import axios from "axios";
import { store } from "../store.js";

import SearchBar from "./SearchBar.vue";
import SectionCharacters from "./SectionCharacters.vue";

export default {
  name: "AppMain",
  components: {
    SearchBar,
    SectionCharacters,
  },
  data() {
    return {
      store,
    };
  },
  methods: {
    getCharacters(data = "") {
      if (data === "reset") {
        this.store.searchText = "";
        this.store.statusValue = "";
      }

      axios
        .get("https://rickandmortyapi.com/api/character", {
          params: {
            name: this.store.searchText,
            status: this.store.statusValue,
          },
        })
        .then((resp) => {
          this.store.characters = resp.data.results;
        })
        .catch((err) => {
          this.store.characters = [];
        });
    },
  },
  created() {
    this.getCharacters();
  },
};
</script>
<template>
  <main class="mt-5">
    <SearchBar @search="getCharacters" />
    <SectionCharacters />
  </main>
</template>
<style lang="scss" scoped></style>
