<template>
  <div>
    <h1>{{ msg }}</h1>
    <h2>Filter Learn Vue Articles</h2>
    <input type="text" name="" id="" placeholder="Filter Search" v-model="query">
    <br>
    <button @click="reset"> Reset </button>
    <search-results :query="query"></search-results>
  </div>
</template>

<script>
import { ref } from "vue";
import SearchResults from './SearchResults.vue'

export default {
  props: {
    msg: String,
  }, 
  components: {
    SearchResults, 
  }, 
  setup() {
    const query = ref("");
    const reset = () => {
      query.value = ''
    }
    return {
      reset, 
      query,
    };
  },
};
</script>

<style>
  input[type='text'] {
    margin-bottom: 20px;
    padding: 10px;
  }
</style>