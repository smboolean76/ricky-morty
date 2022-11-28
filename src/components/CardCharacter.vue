<script>
export default {
  name: "CardCharacter",
  props: {
    info: Object,
  },
};
</script>

<template>
  <div class="text-center">
    <img class="rounded-circle img-fluid" :src="info.image" :alt="info.name" />
    <h3 class="mb-3">{{ info.name }}</h3>
    <div class="status">{{ info.status }}</div>
    <div class="race">{{ info.species }}</div>
  </div>
</template>

<style lang="scss" scoped></style>
