<template>
  <div id="app">
    <TheHeader />
    <SearchQuery></SearchQuery>
    <SearchWhat />
    <CategoriesSlider></CategoriesSlider>
    <VProducts></VProducts>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';
import TheBreadcrumbs from './components/TheBreadcrumbs.vue';
import ContactsForm from './components/ContactsForm.vue';
import SearchQuery from './components/SearchQuery.vue';
//import VProducts from './components/VProducts.vue';
import CategoriesSlider from './components/CategoriesSlider.vue';
import SearchWhat from './components/SearchWhat.vue';
import VProducts from './components/VProducts.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheBreadcrumbs,
    ContactsForm,
    TheFooter,
    SearchQuery,
    VProducts,
    CategoriesSlider,
    SearchWhat,
  }
}
</script>

<style lang="scss">
@import './assets/scss/style';

#app {

  overflow: hidden;

}
</style>
