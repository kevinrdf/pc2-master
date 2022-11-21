<script>
import countries from "/src/datasets/countries.json";
import CountryComponent from "../components/CountryComponent.vue";

export default {
  name: "CountriesView",
  components: {
    CountryComponent,
  },
  data() {
    return {
      countries: [],
      paisActual: "",
    };
  },
  created() {
    this.countries = countries;
  },
  methods: {
    setPaisActual(e) {
      const filtro = e.target.value;
      this.paisActual = filtro;
      this.countries = countries.filter((country) =>
        country.name.toLowerCase().includes(filtro)
      );
    },
  },
};
</script>

<template>
  <div class="countries">
    <input
      placeholder="Busca un país"
      :value="this.paisActual"
      @input="setPaisActual"
    />
  </div>
  <div class="countries-container">
    <CountryComponent
      v-for="(country, index) in countries"
      :key="index"
      :name="country.name"
      :capital="country.capital"
      :currency_name="country.currency_name"
      :currency="country.currency"
      :region="country.region"
      :code="country.iso2"
      :clickable="true"
    ></CountryComponent>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  .countries {
    display: flex;
    align-items: center;
  }

  input {
    line-height: 2em;
  }

  .countries-container {
    text-align: center;
    overflow-y: auto;
    vertical-align: middle;
    display: grid;
    grid-template-columns: auto auto auto;
    grid-gap: 10px;
    padding: 10px;
  }
}
</style>
