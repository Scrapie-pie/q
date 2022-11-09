<template>
  <div id="app">
    <TheHeader />
    <SearchQuery></SearchQuery>
    <TheBreadcrumbs />
    <ContactsForm />
    <TheFooter />
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheFooter from './components/TheFooter.vue';
import TheBreadcrumbs from './components/TheBreadcrumbs.vue';
import ContactsForm from './components/ContactsForm.vue';
import SearchQuery from './components/SearchQuery.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    TheBreadcrumbs,
    ContactsForm,
    TheFooter,
    SearchQuery
  }
}
</script>

<style lang="scss">
@import './assets/scss/style';

#app {
  overflow: hidden;
}
</style>
