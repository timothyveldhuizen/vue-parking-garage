<template>
<div>
  <h1>Parking Garages</h1>
  <SearchPlace @handleSearchTextChange="onSearchTextChange" />
  <SearchFilter @handleSearchFilterChange="onSearchFilterChange" />
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
  components: {
    SearchPlace,
    SearchFilter,
    ParkingGarageList,
  },
  data() {
    return {
      listParkingGarages: dataParkingGarageList,
    }
  },
  methods: {
    onSearchTextChange(place) {
      this.listParkingGarages = dataParkingGarageList
        .filter(item => item.place ? item.place.toLowerCase().includes(place.toLowerCase()) : false)
    },
    onSearchFilterChange(parkingFilterTypes) {
      this.listParkingGarages = dataParkingGarageList
        .filter(item => parkingFilterTypes ? parkingFilterTypes.includes(item.parkingaddresstype) : false)
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
