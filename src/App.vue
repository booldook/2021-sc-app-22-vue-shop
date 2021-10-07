<template>
  <div class="container my-3">
    <Title :title="mainTitle" />
    <Search @@change="onChangeQuery" />
    <ListWrap />
    <div></div>
  </div>
</template>

<script>
import axios from 'axios';
import Title from './components/TitleCp.vue';
import Search from './components/SearchCp.vue';
import ListWrap from './components/ListWrapCp.vue';

export default {
  name: 'App',
  components: { Title, Search, ListWrap },
  data() {
    return {
      mainTitle: '다팔아 쇼핑몰',
      query: '',
      foods: [],
    };
  },
  async created() {
    const { data } = await axios.get('/json/foods.json');
    this.foods = data;
  },
  methods: {
    onChangeQuery(v) {
      this.query = v;
    },
  },
};
</script>

<style lang="scss" scoped>
@import '@/assets/scss/_common.scss';
</style>
