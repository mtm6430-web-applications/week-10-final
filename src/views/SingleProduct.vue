<template>
  <div>
    <ProductInfo :product="product" />
  </div>
</template>
<script>
import { mapGetters } from "vuex";
import ProductInfo from "@/components/ProductInfo.vue";
export default {
  watch: {
    $route(to, from) {
      // react to route changes...
      console.log(to);
    }
  },
  components: { ProductInfo },
  name: "single-product",
  data() {
    return { product: "" };
  },
  props: { id: { required: true } },
  created() {
    console.log(parseInt(this.id));
    this.product = this.getProductById(parseInt(this.id));
    console.log(this.product);
  },
  computed: {
    ...mapGetters(["getProductById"])
  }
};
</script>
