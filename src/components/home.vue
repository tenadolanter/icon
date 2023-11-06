<template>
  <div class="home-wrap">
    <Header :query="query" @on-change="handlerQueryChange"></Header>
    <Icons :query="query"></Icons>
  </div>
</template>

<script>
import Header from "./header.vue";
import Icons from "./icons.vue";
export default {
  components: {
    Header,
    Icons,
  },
  data() {
    return {
      query: "",
    };
  },
  methods: {
    handlerQueryChange(query) {
      this.query = query;
    },
  },
};
</script>

<style scoped lang="scss">
.home-wrap {
  max-width: 1320px;
  margin: 0 auto;
}
</style>
