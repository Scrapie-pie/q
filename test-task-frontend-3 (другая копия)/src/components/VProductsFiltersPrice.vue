<template>
  <div class="v-products-filters-price">
    <span class="caption">Цена, валюта</span>
    <form>
      <div class="price-view">
        <span class="price-text">от</span>

        <!-- <input v-model="value[0]" class="input-box"/> -->
        <BaseInput v-model="value[0]" mod="primary"></BaseInput>
        <span class="price-text">до</span>
        <BaseInput v-model="value[1]" mod="primary"></BaseInput>
        <span class="price-text">Р</span>
      </div>

      <VRange v-model="value" :settings="rangeSettings"></VRange>
    </form>

  </div>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
import BaseField from './BaseField.vue';
import BaseButton from './BaseButton.vue';
import BaseContainer from './BaseContainer.vue';
import VRange from './VRange.vue';
import BaseInput from './BaseInput.vue';
export default {
  name: 'VProductsFiltersPrice',
  data() {
    return {
      value: [1000, 1000000],
      rangeSettings: {
        dotSize: 14,
        //height: '8px',
        tooltip: 'always',
        tooltipPlacement: 'bottom',
        min: 0,
        max: 1000000,
      }
    }
  },
  methods: {
    numberWithCommas(x) {
      return +x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, " ");
    }
  },
  components: {
    BaseIcon,
    BaseField,
    BaseButton,
    BaseContainer,
    VRange,
    BaseInput
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/scss/common';

.v-products-filters-price {

  .caption {
    font-weight: 700;
  }

  .input-box {
    width: 110px;
    height: 40px;
    left: 62px;
    top: 728px;
    border: 1px solid #DEDEDE;
    border-radius: 3px;
    padding: 12px 13px;

    &::-webkit-outer-spin-button,
    &::-webkit-inner-spin-button {
      -webkit-appearance: none;
      margin: 0;
    }

    /* Firefox */
    &[type=number] {
      -moz-appearance: textfield;
    }
  }

  .price-view {
    @include flex-it(row, 10px);
    align-items: center;
    margin: 16px 0 14px;

  }
  .price-text {
    font-size: 12px;
    opacity: .5;
  }

}
</style>
