<template>
  <div id="home">
    <!-- Page Wrapper -->
    <div id="background-div" class="page-holder bg-cover">
      <div class="container py-5">
        <header class="text-left text-white py-5">
          <h3 class="mb-4 rounded">
            <a
              href="#start-shopping"
              class="bg-white px-2 py-2 rounded"
              id="heading"
              >Start Shopping</a
            >
          </h3>
          <p id="content" class="lead mb-0 bg-dark p-1 rounded">
            Simple Coding Market is for educational purposes only. It can be
            used by developers to learn about developing an ecommerce
            application complete with backend and frontend for Web and Android
          </p>
        </header>
        <p class="text-center text-black">Designed By Patrick Afriyie Wilson</p>
      </div>
    </div>

    <div id="start-shopping" class="container">
      <div class="row">
        <div class="col-12 text-left">
          <h2 class="pt-3">Top Categories</h2>
        </div>
      </div>
      <div class="row">
        <div
          v-for="index in this.categorySize"
          :key="index"
          class="col-md-6 col-xl-4 col-12 pt-3 justify-content-around d-flex"
        >
          <CategoryBox :category="categories[index - 1]"> </CategoryBox>
        </div>
      </div>
    </div>

    <hr />
    <div class="container">
      <div class="row">
        <div class="col-12 text-left">
          <h2 class="pt-3">Top Products</h2>
        </div>
      </div>
      <div class="row">
        <div
          v-for="index in this.productSize"
          :key="index"
          class="col-md-6 col-xl-4 col-12 pt-3 justify-content-around d-flex"
        >
          <ProductBox :product="products[index - 1]"> </ProductBox>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CategoryBox from "@/components/Category/CategoryBox.vue";
import ProductBox from "@/components/Category/ProductBox.vue";

export default {
  name: "HomeView",
  components: { CategoryBox, ProductBox},
  props: ["categories", "products"],
  data() {
    return {
      categorySize: 0,
      productSize: 0,
    };
  },
  mounted() {
    this.categorySize = Math.min(6, this.categories.length);
    this.productSize = Math.min(8, this.products.length);
  },
};
</script>

<style>
.page-holder {
  min-height: 100vh;
}

.bg-cover {
  background-size: cover !important;
}

#background-div {
  background: url(../assets/home.png);
}

#heading {
  text-decoration: none;
  font-family: "Roboto", sans-serif;
  font-weight: 400;
  opacity: 0.8;
  font-family: "Josefin Sans", sans-serif;
}

#content {
  opacity: 0.8;
}

h2 {
  font-family: "Josefin Sans", sans-serif;
}
</style>
