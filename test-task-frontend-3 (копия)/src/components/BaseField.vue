<template>
  <label class="field" :class="[filledClass, `field-${type}`]">
    <span v-if="label" class="field-name">
      {{label}}
    </span>
    <div :class="`field-wrapper`">
      <div class="field-action">
        <BaseIcon v-if="icon" :icon="icon" class="field-icon" />
        <div class="field-fit">
          <BaseTextarea
            v-if="type === 'textarea'"
            v-bind="$attrs"
            v-on="listeners"
          />
          <BaseInput
            v-else
            v-bind="$attrs"
            v-on="listeners"
            :type="type"
            ref="input"
          />
          <span
            v-if="placeholder"
            v-show="isShowingPlaceholder"
            class="field-placeholder"
            :class="placeholderClass"
          >
            {{placeholder}}
          </span>
        </div>
        <slot name="right"></slot>
      </div>
    </div>
  </label>
</template>

<script>
import BaseInput from './BaseInput.vue';
import BaseTextarea from './BaseTextarea.vue';
import BaseLabel from './BaseLabel.vue';
import BaseIcon from './BaseIcon.vue';
import BaseButton from './BaseButton.vue';

export default {
  name: 'BaseField',
  data() {
    return {
      isMounted: false,
      isShowingPlaceholder: true,
      filledClass: '',
    }
  },
  props: {
    type: {
      type: String,
      default: 'text',
    },
    isPopupPlaceholder: {
      type: Boolean,
      default: false
    },
    label: String,
    placeholder: String,
    icon: String,
  },
  inheritAttrs: false,
  computed: {
    placeholderClass() {
      if (this.isPopupPlaceholder) {
        return `field-placeholder--popup`
      }
    },
    listeners() {
      let vm = this;

      return Object.assign({},
        this.$listeners,
        {
          input(value) {
            vm.$emit('input', value);
            vm.showingPlaceholder(value);
            vm.filledClassHandler(value);
          },
        }
      )
    },
  },
  methods: {
    showingPlaceholder(inputValue) {
      this.isShowingPlaceholder = !this.isPopupPlaceholder && !inputValue.length;
    },
    filledClassHandler(inputValue) {
      this.filledClass = inputValue.length ? 'field_filled' : '';
    }
  },
  components: {
    BaseInput,
    BaseTextarea,
    BaseLabel,
    BaseIcon,
    BaseButton
  }
}
</script>

<style lang="scss">
//background: #CCCCCC;

.field {
  $self: &;

  width: 100%;
  @include flex-it(column, 10px);

  &-name {
    color: get-var(color, grey_dark);
    width: min-content;
  }

  #{$self}-action {
    position: relative;
    display: flex;
    align-items: center;
    padding-bottom: 4px;
    width: 100%;


    @include h(3, $color: #343434, $weight: 300);

    font-size: 26px;
    font-weight: 300;
    border-bottom: 1px solid #E2E2E2;
  }

  #{$self}-fit {
    width: 100%;
    position: relative;
  }

  #{$self}-placeholder {
    position: absolute;
    width: 100%;
    left: 0;
    pointer-events: none;
    @include h(3, $color: #CCCCCC, $weight: 300);
    //color: #CCCCCC;
    transition: .25s ease-out;
  }

  &-text, &-password, &-mail {
    #{$self}-placeholder {
      top: 50%;
      transform: translateY(-50%);
    }
  }

  .input, .textarea {
    width: 100%;
    font-weight: 300;

    &[required] + #{$self}-placeholder {
      &:after {
        content: ' *';
        color: #FF1300;
      }
    }
  }

  &-textarea {
    padding-top: 60px;
    .textarea {
      height: 1em;
      overflow: hidden;
    }

    #{$self}-placeholder {
      bottom: 60px;
    }
  }

  .input:focus + #{$self}-placeholder--popup {
    font-size: 16px;
    top: -10px;
    transition: .1s ease-in;
  }

  &_filled {
    .input + #{$self}-placeholder--popup {
      font-size: 16px;
      top: -10px;
      transition: .1s ease-in;
    }
  }
}
</style>
