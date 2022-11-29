<script>
import { store } from "../store";

export default {
  name: "AppFooter",
  data() {
    return {
      store,
    };
  },
  computed: {
    totalCharatersAlive() {
      // let counter = 0;
      // this.store.characters.forEach((elm) => {
      //   if (elm.status === "Alive") {
      //     counter++;
      //   }
      // });
      // return counter;
      return this.store.characters.filter((elm) => elm.status === "Alive")
        .length;
    },
    charactersDead() {
      return this.store.characters.filter((elm) => elm.status === "Dead");
    },
    totalCharaters() {
      return this.store.characters.length;
    },
  },
};
</script>
<template>
  <footer class="container text-center">
    <h3>Totale personaggi: {{ totalCharaters }}</h3>
    <h3>Totale personaggi vivi: {{ totalCharatersAlive }}</h3>
  </footer>
</template>

<style lang="scss" scoped></style>
