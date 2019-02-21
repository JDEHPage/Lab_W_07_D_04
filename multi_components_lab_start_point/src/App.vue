<template lang="html">
  <div>
    <h1>Countries</h1>
    <div class="main-container">
      <selected-country :countries='countries'></selected-country>
      <!-- <countries-list :countries='countries'></countries-list> -->
      <country-detail :country='selectedCountry'></country-detail>
    </div>
  </div>
</template>

<script>
import CountrySelect from './components/CountrySelect.vue';
// import CountryList from './components/CountryList.vue';
import CountryDetails from './components/CountryDetails.vue';
import { eventBus } from './main.js'

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(res => res.json())
    .then(countries => this.countries = countries)

    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    });
  },
  components: {
    'selected-country': CountrySelect,
    // 'countries-list': CountryList,
    'country-detail': CountryDetails
  }





}
</script>

<style lang="css" scoped>
  .main-container {
    display: flex;
    justify-content: space-between;
  }
</style>
