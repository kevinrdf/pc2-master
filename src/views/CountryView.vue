<script>
import countries from "/src/datasets/countries.json";

export default {
  name: "CountriesView",
  components: {},
  data() {
    return {
      country: {},
    };
  },
  created() {
    this.country = countries.find(
      (country) => country.iso2 === this.$route.params.code
    );
  },
  methods: {},
};
</script>

<template>
  <div class="country">
    <h1 class="nombre">{{ country.name }}</h1>
    <img
      width="400"
      height="400"
      :src="`https://countryflagsapi.com/png/${country.iso2}`"
    />
    <h1>{{ name }}</h1>
    <h2>{{ `Capital: ${country.capital}` }}</h2>
    <h3>{{ `Moneda: ${country.currency_name} (${country.currency})` }}</h3>
    <h3>{{ `Región: ${country.region}` }}</h3>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
}

.nombre {
  font-size: 50px;
}
</style>
