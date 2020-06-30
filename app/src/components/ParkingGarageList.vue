<template>
<div>
  <span>Number of results {{list.length}}</span>
  <ParkingGarageItem v-for="item in list" :key="item.parkingaddressreferencetype + item.parkingaddressreference + item.parkingaddresstype" :parking-garage="item" />
</div>
</template>

<script>
import ParkingGarageItem from './ParkingGarageItem';

export default {
  name: 'ParkingGarageList',
  props: ['list'],
  components: {
      ParkingGarageItem,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
