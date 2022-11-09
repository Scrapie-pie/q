<template>
  <VueSlider class="v-range" v-bind="settings" :value="value" @change="change">


  </VueSlider>
</template>

<script>
import VueSlider from 'vue-slider-component'
import 'vue-slider-component/theme/default.css'

export default {
  name: 'VRange',
  props: {
    value: {
      required: false,
      default: '',
    },
    settings: {
      type: Object,
      // default() {
      //   return {
      //     dotSize: ['auto', 'auto'],
      //     height: '8px',
      //     tooltip: 'always',
      //     tooltipPlacement: 'bottom',
      //     min: 0,
      //     max: 1000000,
      //   }
      // }
    }
  },
  computed: {
    rangeSettings() {
      return {

      }
    },
  },

  methods: {
    change(e) {
      this.$emit('input', e)
    },
  },
  components: {
    VueSlider,
  },
}
</script>

<style lang="scss">
.v-range {
  .vue-slider-rail {
    height: 4px;
    background-color: black;
  }
  .vue-slider-process {
    background-color: black;
  }
  .vue-slider-dot-handle {
    border: 2px solid black;
    box-shadow: none;
  }
}
</style>
