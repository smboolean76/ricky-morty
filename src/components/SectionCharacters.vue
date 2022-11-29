<script>
import { store } from "../store.js";

import CardCharacter from "./CardCharacter.vue";

export default {
  name: "SectionCharacters",
  components: {
    CardCharacter,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <section class="container py-4">
    <div class="row g-3" v-if="store.characters.length > 0">
      <CardCharacter
        v-for="character in store.characters"
        class="col-sm-6 col-lg-3"
        :info="character"
      />
    </div>
    <h3 v-else>Nessun risultato</h3>
  </section>
</template>

<style lang="sass" scoped></style>
