<template>
  <div class="search-wrap">
    <div class="search-input-wrap">
      <input class="search-input" v-model="locQuery" @change="handlerQueryChange" type="text" placeholder="搜索图标..." />
    </div>
    <button class="search-button-wrap">
      <span class="search-icon ticon-search-fill"></span>
      <span>搜索</span>
    </button>
  </div>
</template>

<script>
export default {
  props: {
    query: {
      type: String,
      default: "",
    },
  },
  data(){
    return {
      locQuery: "",
    }
  },
  watch: {
    query: {
      immediate: true,
      handler(newVal, oldVal) {
        if(newVal === oldVal) return;
        this.locQuery = newVal;
      }
    },
  },
  methods: {
    handlerQueryChange(){
      this.$emit('on-change', this.locQuery);
    },
  },
};
</script>

<style scoped lang="scss">
.search-wrap {
  margin-top: 32px;
  display: flex;
  align-items: center;
  column-gap: 16px;
  .search-input-wrap {
    display: flex;
    align-items: center;
    width: 480px;
    height: 56px;
    border-radius: 4px;
    transition: all 0.2s ease-out;
    box-shadow: 0 0 1px rgba(96, 96, 96, 0.31),
      0 4px 8px -2px rgba(96, 96, 96, 0.15);
    border: 1.5px solid transparent;
    &:focus-within {
      border-color: #1fb141;
      box-shadow: 0 0 0 1.5px rgba(31, 177, 65, 0.08);
    }
    .search-input {
      flex: 1 0 0;
      height: 40px;
      padding: 0 14px;
      font-size: 1rem;
      font-style: normal;
      font-weight: 400;
      line-height: 20px;
      outline: none;
      color: #1a1a1a;
    }
  }
  .search-button-wrap {
    background-color: rgba(0, 0, 0, 0.9);
    font-size: 16px;
    border-radius: 4px;
    font-weight: 600;
    height: 56px;
    color: #fff;
    cursor: pointer;
    display: flex;
    align-items: center;
    flex-shrink: 0;
    padding: 16px 24px;
    .search-icon {
      margin-right: 6px;
    }
  }
}
</style>
