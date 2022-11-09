<template>
  <div class="v-products-filters-brand">
    <div class="top">
      <span class="caption">Бренды</span>
      <span class="reset" @click="reset">Очистить</span>
    </div>

    <form class="form">
      <VCheckbox value="foo" v-model="checkedBrands">
        <span>Бренд<AmountInline value="xxx" /></span>
      </VCheckbox>
      <VCheckbox value="bar" v-model="checkedBrands">
        <span>Бренд<AmountInline value="x" /></span>
      </VCheckbox>
      <VCheckbox value="baz" v-model="checkedBrands">
        <span>Бренд<AmountInline value="x xxx" /></span>
      </VCheckbox>
    </form>
  </div>
</template>

<script>
import AmountInline from './AmountInline.vue';
import VCheckbox from './VCheckbox.vue';
export default {
  name: 'VProductsFiltersBrand',
  data() {
    return {
      checkedBrands: []
    }
  },
  methods: {
    reset() {
      this.checkedBrands = [];
    }
  },
  components: {
    AmountInline,
    VCheckbox
  }
}
</script>

<style lang="scss" scoped>
.v-products-filters-brand {
  .top {
    @include flex-it(row, 15px);
    justify-content: space-between;
    margin-bottom: 14px;
  }

  .caption {
    font-weight: 700;
  }

  .reset {
    font-size: 10px;
    text-decoration-line: underline;
    color: #333333;
    opacity: 0.5;
    cursor: pointer;
  }

  .form {
    @include flex-it(column, 15px);
  }
}
</style>
