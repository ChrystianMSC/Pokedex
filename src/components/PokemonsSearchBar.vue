<template>
  <v-container class="search-bar-container">
    <v-row>
      <v-col cols="12" class="d-flex justify-center">
        <img height="40" :src="require('../assets/logo.png')" alt="" />
      </v-col>
    </v-row>
    <v-row>
      <v-text-field
        class="text-field roundex-xl"
        label="Search for Pokemon"
        filled
        rounded
        dense
        hint="For example, Charmander..."
        v-model="search"
        @keydown.enter="emitSearch()"
      ></v-text-field>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    search: "",
  }),
  methods: {
    emitSearch() {
      this.$emit("search-event", this.search.toLowerCase());
    },
  },
};
</script>

<style lang="scss" scoped>
.search-bar-container {
  & .v-row > .text-field {
    width: 500px;
    margin-right: 50px;
  }
}
</style>
