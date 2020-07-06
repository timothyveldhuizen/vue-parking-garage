<template>
<div>
<input type="checkbox" id="a" value="A" v-model="parkingFilterTypes">
<label for="a">Administratief adres</label>
<input type="checkbox" id="p" value="P" v-model="parkingFilterTypes">
<label for="p">Postadres</label>
<input type="checkbox" id="f" value="F" v-model="parkingFilterTypes">
<label for="f">Feitelijk adres</label>
</div>
</template>

<script>
export default {
  name: 'SearchFilter',
  props: ['parkingFilterTypes'],
  watch: {
    parkingFilterTypes: {
      handler: function(newValue) {
        this.$emit('handleSearchFilterChange', newValue)
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
