<template>
  <div class="row">
    <h1 class="col-12">Products List</h1>
    <div class="col-sm-4 p-1" v-for="product in products" :key="product.id">
      <ProductCard :product="product" />
    </div>
  </div>
</template>
<script>
// Importing ProductCard component
import ProductCard from "@/components/ProductCard.vue";

// Importing the mapState function from vuex which allows us to map our state properties directly to component's computed properties
import { mapState } from "vuex";

export default {
  created() {
    this.$store.dispatch("fetchData");
  },
  // using mapState function to auto create computed property products who's value will be set to our state property products
  computed: mapState(["products"]),
  components: { ProductCard }
};
</script>
