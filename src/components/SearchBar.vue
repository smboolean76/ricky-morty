<script>
import { store } from "../store.js";

export default {
  name: "SearchBar",
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
    <form
      class="row justify-content-center gx-2"
      @submit.prevent="$emit('search')"
    >
      <div class="col-auto">
        <input
          type="text"
          class="form-control w-auto"
          placeholder="Search character"
          v-model="store.searchText"
        />
      </div>
      <div class="col-auto">
        <select
          class="form-select w-auto"
          name="status"
          v-model="store.statusValue"
        >
          <option value="" selected>Select status</option>
          <option value="alive">Alive</option>
          <option value="dead">Dead</option>
          <option value="unknown">Unknown</option>
        </select>
      </div>
      <div class="col-auto">
        <button class="btn btn-primary" type="submit">Search</button>
      </div>
      <div class="col-auto">
        <button
          class="btn btn-warning"
          type="reset"
          @click="$emit('search', 'reset')"
        >
          Reset
        </button>
      </div>
    </form>
  </div>
</template>

<style lang="scss" scoped></style>
