<template>
<div>
  <h1>Parking Garages</h1>
  <SearchPlace @handleSearchTextChange="onSearchTextChange" />
  <SearchFilter @handleSearchFilterChange="onSearchFilterChange" />
  <ParkingGarageList :list="filteredListParkingGarages" />
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
      filterPlace: '',
      filterType: [],
      listParkingGarages: dataParkingGarageList,
    }
  },
  computed: {
    filteredListParkingGarages() {
      return dataParkingGarageList
        .filter(item => item.place ? item.place.toLowerCase().includes(this.filterPlace.toLowerCase()) : false)
        .filter(item => item.parkingaddresstype ? this.filterType.includes(item.parkingaddresstype) : false)
    }
  },
  methods: {
    onSearchTextChange(place) {
      this.filterPlace = place;
    },
    onSearchFilterChange(parkingFilterTypes) {
      this.filterType = parkingFilterTypes;
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
