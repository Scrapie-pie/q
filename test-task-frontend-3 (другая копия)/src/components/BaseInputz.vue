<template>

  <div
    v-if="isContentEditable"
    class="input"
    contenteditable="true"
    @input="onInputz"
    v-bind="$attrs"
    ref="editableBlock"
  >{{customValue}}</div>

    <!-- <div


    <input
      v-if="!isContentEditable"
      class="input"
      :type="type"
      :placeholder="placeholder"
      @input="onInput"
      v-bind="$attrs"
      ref="input"
    >

  </div> -->

</template>

<script>
//import BaseLabel from './BaseLabel.vue';
export default {
  name: "BaseInput",
  data() {
    return {
      customValue: 'qwery',
      isMounted: false,
    }
  },
  inheritAttrs: false,
  props: {
    label: String,
    type: {
      type: String,
      validator: (value) => ['text', 'mail', 'password'].includes(value),
      default: "text",
    },
    placeholder: String,
    isContentEditable: {
      type: Boolean,
      default: false,
    },
    resizeble: {
      type: Boolean,
      default: false,
    }

  },
  // updated() {
  //   //do something after updating vue instance
  //   if (this.isMounted) {
  //     console.log(this.customValue);
  //     console.log(this.$refs.editableBlock.innerHTML);
  //   }
  // },
  mounted() {
    let vm = this
    //do something after mounting vue instance
    this.isMounted = true;
    //console.log(this.$refs)
    this.$refs.editableBlock.addEventListener("input", function(e) {
    this.customValue = e.target.innerText
    //console.log(e.target.innerText)
    //console.log(this.customValue)
    // console.log("input event fired");
    // console.log(vm.value)
    // vm.$emit('input', vm.customValue);
}, false);

},
methods: {
  onInputz(e) {
    //console.log(e)
    console.log(e.target.innerText)
    this.customValue = e.target.innerText;
    this.$emit('input', this.customValue);
    console.log(this.customValue)
  }
}
  // methods: {
  //   onInput(q) {
  //     console.log(q)
  //     this.$emit('input', $event.target.value);
  //     if (this.resizable) {
  //       this.resizable(this.$refs.input.$el,7);
  //     }
  //   },
  //   resizable (el, factor) {
  //     var int = Number(factor) || 7.7;
  //     function resize() {el.style.width = ((el.value.length+1) * int) + 'px'}
  //     var e = 'keyup,keypress,focus,blur,change'.split(',');
  //     for (var i in e) el.addEventListener(e[i],resize,false);
  //     resize();
  //   }
  // },
  // mounted() {
  // }

}
</script>

<style lang="scss">
.input {
  background-color: transparent;
  font-family: inherit;
  font-size: inherit;
  font-weight: inherit;
  color: currentColor;
  outline: none;
  padding: 0;
  border: none;

  &[type="text"], &[type="password"], &[type="email"] {
    background-color: transparent;
    width: 100%;
    height: 100%;
    cursor: text;
  }

  // &[type="checkbox"] {
  //   $size: 16px;
  //   background-color: transparent;
  //   max-width:  $size;
  //   max-height: $size;
  //   min-width:  $size;
  //   min-height: $size;
  //   margin: 0;
  // }
}
</style>
