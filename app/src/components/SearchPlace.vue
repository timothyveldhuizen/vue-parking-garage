<template>
<div>
  <label for="searchplace">Search place</label>
  <input type="text" v-model="searchQuery" @keyup="onInputTextChange()" id="searchplace"/>
</div>
</template>

<script>
export default {
  name: 'SearchPlace',
  data() {
    return {
      searchQuery: '',
    }
  },
  methods: {
    onInputTextChange() {
      this.$emit('handleSearchTextChange', this.searchQuery);
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
