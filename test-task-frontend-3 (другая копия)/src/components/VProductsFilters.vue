<template>
  <div class="v-products-filters">
    <VProductsFiltersCategories class="categories"/>
    <VProductsFiltersPrice class="price"/>
    <VProductsFiltersBrand class="brand"/>
  </div>
</template>

<script>
import VProductsFiltersCategories from './VProductsFiltersCategories.vue';
import VProductsFiltersPrice from './VProductsFiltersPrice.vue';
import VProductsFiltersBrand from './VProductsFiltersBrand.vue';
export default {
  name: 'ProductsFilters',
  data() {
    return {
      value: ''
    }
  },
  components: {
    VProductsFiltersCategories,
    VProductsFiltersPrice,
    VProductsFiltersBrand
  }
}
</script>

<style lang="scss" scoped>
.v-products-filters {

  .categories {
    margin-bottom: 45px;
  }
  .price {
    margin-bottom: 30px;
  }
}
</style>
