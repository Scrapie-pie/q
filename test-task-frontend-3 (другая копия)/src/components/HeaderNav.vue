<template>
  <nav class="header-nav">
    <a href="#" class="header-nav-item">Проекты</a>
    <a href="#" class="header-nav-item">О компании</a>
    <a href="#" class="header-nav-item active">Контакты</a>
  </nav>
</template>

<script>

export default {
  name: 'HeaderNav',
  components: {
  }
}
</script>

<style lang="scss">
.header-nav {
  //@include flex-it(row, 50px);
  display: flex;
  @include to-responsive(gap, 15px, 50px);

  &-item {
    color: get-var(color, dark);
    font-weight: 600;

    &.active {
      color: get-var(color, blue_light);
      @include under-dot(7px);
    }
  }

  @include media($max: lg) {
    display: none;
  }
}
</style>
