<template>
  <div class="header-wrap">
    <div class="left">
      <div class="h1">定制自己的字体图标库</div>
      <div class="h3">
        欢迎来到我定制的字体图标库，这是一个专为个人和小团体设计的独特资源，旨在为您的项目和创意提供独特的图标解决方案。我们深知字体图标在设计中的重要性，因此我们特意打造了这个库，以满足您对美感和个性化的需求。
      </div>
      <Search :query="query" @on-change="query => $emit('on-change', query)"></Search>
    </div>
    <div class="right">
      <img class="icon" :src="IconImage" />
    </div>
  </div>
</template>

<script>
import IconImage from "../assets/icons.png";
import Search from "./search.vue";
export default {
  components: {
    Search,
  },
  props: {
    query: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      IconImage,
    };
  },
};
</script>

<style scoped lang="scss">
.header-wrap {
  display: flex;
  align-items: center;
  padding-top: 3rem;
  padding-bottom: 3rem;
  font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue",
    "Noto Sans", "Liberation Sans", Arial, sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  .left {
    .h1 {
      font-size: 3rem;
      line-height: 1.2;
      font-weight: 500;
      margin-bottom: 1.5rem;
      color: #212529;
    }
    .h3 {
      font-size: 1.5rem;
      line-height: 1.5;
      margin-bottom: 0.5rem;
      font-weight: 500;
      color: #212529;
    }
  }
  .right {
    flex: 0 0 auto;
    width: 36.666667%;
    .icon {
      max-width: 100%;
      height: auto;
      margin: 1rem 0;
    }
  }
}
</style>
