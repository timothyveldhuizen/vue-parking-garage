<template>
  <div>
    <h1>{{parkingGarage.streetname}} {{parkingGarage.housenumber}}</h1>
    <h2>{{parkingGarage.zipcode}} {{parkingGarage.place}}</h2>
    <h3>{{parkingGarage.province}}</h3>
    <p>{{parkingGarage.parkingaddresstype}}</p>
  </div>
</template>

<script>
export default {
  name: "ParkingGarageItem",
  props: ["parkingGarage"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
