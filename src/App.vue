<template>
  <div class="container my-3">
    <Title :title="mainTitle" />
    <Search />
  </div>
</template>

<script>
import Title from './components/TitleCp.vue';
import Search from './components/SearchCp.vue';

export default {
  name: 'App',
  data() {
    return {
      mainTitle: '다팔아 쇼핑몰',
    };
  },
  components: { Title, Search },
};
</script>

<style lang="scss">

</style>
