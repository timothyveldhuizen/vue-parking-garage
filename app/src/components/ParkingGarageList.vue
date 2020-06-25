<template>
<div>
  <p>Parking Garage List feature</p>
  <ParkingGarageItem />
</div>
</template>

<script>
import ParkingGarageItem from './ParkingGarageItem';

export default {
  name: 'ParkingGarageList',
  components: {
      ParkingGarageItem,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
