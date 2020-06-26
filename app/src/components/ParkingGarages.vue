<template>
<div>
  <SearchPlace />
  <SearchFilter />
  <ParkingGarageList :list="listParkingGarages" />
</div>
</template>

<script>
import SearchPlace from './SearchPlace';
import SearchFilter from './SearchFilter';
import ParkingGarageList from './ParkingGarageList';
import dataParkingGarageList from '../data/DataParkingGarageList';

export default {
  name: 'ParkingGarages',
  data() {
    return {
      listParkingGarages: dataParkingGarageList,
    }
  },
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
