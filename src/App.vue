<template>
  <div class="container my-3">
    <Title :title="mainTitle" />
    <Search @@change="onChangeQuery" />
    <ListWrap @@click="onChangeList" :lists="foods" />
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
    onChangeList(v) {
      console.log(v);
    },
  },
};
</script>

<style lang="scss">
/* 여기에 주석이라도 있어야 scss-loader가 실행된다. */
</style>
