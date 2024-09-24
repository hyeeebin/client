<template>
  <h1>hello~~</h1>
  <div :key="i" v-for="(product,i) in productList">
    <span>{{product.name}}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      productList: []
    };
  },
  created() {
    this.getProductList();
  },
  methods: {
    async getProductList() {
      this.productList = await this.$api("/api/hello",{});
      console.log(this.productList);
    }
  }
}
</script>