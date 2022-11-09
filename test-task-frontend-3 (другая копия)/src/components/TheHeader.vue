<template>
  <header class="header">
    <BaseContainer>
      <div class="header-logo">Шапка сайта</div>
    </BaseContainer>
  </header>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
import BaseButton from './BaseButton.vue';
import HeaderSearch from './HeaderSearch.vue';
import BaseContainer from './BaseContainer.vue';

export default {
  name: 'TheHeader',
  components: {
    BaseButton,
    BaseIcon,
    HeaderSearch,
    BaseContainer
  }
}
</script>

<style lang="scss">
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  //gap: 30px;
  width: 100%;
  background-color: black;
  padding: 40px 0;
  margin-bottom: 30px;

  &-logo {
    color: white;
    //@include to-responsive(font-size, 84px, 112px);
  }

}
</style>
