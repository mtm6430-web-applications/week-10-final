<template>
  <div>
    <ProductInfo :product="product" />
  </div>
</template>
<script>
import { mapGetters } from "vuex";
import ProductInfo from "@/components/ProductInfo.vue";
export default {
  components: { ProductInfo },
  name: "single-product",
  data() {
    return { product: "" };
  },
  props: { id: { type: Number, required: true } },
  created() {
    console.log(this.id);
    this.product = this.getProductById(this.id);
  },
  computed: {
    ...mapGetters(["getProductById"])
  }
};
</script>
