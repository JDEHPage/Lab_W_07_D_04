<template lang="html">
  <div v-if="country">
    <h1>{{ country.name }}</h1>
    <p>Capital: {{ country.capital }}</p>
    <p>Cioc: {{ country.cioc }}</p>
    <p>Population: {{ country.population }}</p>
  </div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
