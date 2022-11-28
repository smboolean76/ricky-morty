<script>
import SearchBar from "./SearchBar.vue";
import SectionCharacters from "./SectionCharacters.vue";

export default {
  name: "AppMain",
  components: {
    SearchBar,
    SectionCharacters,
  },
};
</script>
<template>
  <main class="mt-5">
    <SearchBar />
    <SectionCharacters />
  </main>
</template>
<style lang="scss" scoped></style>
