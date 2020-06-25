<template>
<div>
  <SearchPlace />
  <SearchFilter />
  <ParkingGarageList />
</div>
</template>

<script>
import SearchPlace from './SearchPlace';
import SearchFilter from './SearchFilter';
import ParkingGarageList from './ParkingGarageList';

export default {
  name: 'ParkingGarages',
  components: {
    SearchPlace,
    SearchFilter,
    ParkingGarageList,
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
