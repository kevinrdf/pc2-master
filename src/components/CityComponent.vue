<script>
export default {
  name: "CountryComponent",
  props: [
    "name",
    "country_name",
    "country_code",
    "state_name",
    "state_code",
    "latitude",
    "longitude",
  ],
};
</script>

<template>
  <div class="city">
    <h1>{{ name }}</h1>
    <h2>{{ `País: ${country_name} (${country_code})` }}</h2>
    <h3>{{ `Estado: ${state_name} (${state_code})` }}</h3>
    <h3>{{ `Latitud: ${latitude}` }}</h3>
    <h3>{{ `Longitud: ${longitude}` }}</h3>
    <img width="200" height="170" src="/src/assets/city.jpg" />
  </div>
</template>

<style scoped>
.city {
  padding: 2px;
  white-space: nowrap;
  width: 350px;
  height: 350px;
  border-style: solid;
  border-radius: 5px;
  border-color: grey;
}

h1 {
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
