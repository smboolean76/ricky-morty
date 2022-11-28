<script>
import axios from "axios";
import CardCharacter from "./CardCharacter.vue";

export default {
  name: "SectionCharacters",
  components: {
    CardCharacter,
  },
  data() {
    return {
      characters: [],
    };
  },
  created() {
    axios.get("https://rickandmortyapi.com/api/character").then((resp) => {
      this.characters = resp.data.results;
    });
  },
};
</script>

<template>
  <section class="container py-4">
    <div class="row g-3">
      <CardCharacter
        v-for="character in characters"
        class="col-sm-6 col-lg-3"
        :info="character"
      />
    </div>
  </section>
</template>

<style lang="sass" scoped></style>
