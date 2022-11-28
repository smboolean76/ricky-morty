<script>
export default {
  name: "SearchBar",
};
</script>

<template>
  <div class="container">
    <form class="row justify-content-center gx-2" action="">
      <div class="col-auto">
        <input
          type="text"
          class="form-control w-auto"
          placeholder="Search character"
        />
      </div>
      <div class="col-auto">
        <select class="form-select w-auto">
          <option selected>Select status</option>
          <option value="1">One</option>
          <option value="2">Two</option>
        </select>
      </div>
      <div class="col-auto">
        <button class="btn btn-primary" type="submit">Search</button>
      </div>
      <div class="col-auto">
        <button class="btn btn-warning" type="reset">Reset</button>
      </div>
    </form>
  </div>
</template>

<style lang="scss" scoped></style>
