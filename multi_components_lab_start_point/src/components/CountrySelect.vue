<template lang="html">
  <div   >
    <label for="country-selector">Select Country</label>
      <select v-on:change="selectEvent"  id="country-selector" v-model="country">
        <option selected disabled>Please Select a Country</option>
        <option v-for='(country, index) in countries' :value='country' :key='index'>{{ country.name }}</option>

      </select>
  </div>


</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: 'selected-country',
  data(){
    return {
      country: null
    }
  },
  props: ['countries'],
  methods: {
    selectEvent(){
      eventBus.$emit('country-selected', this.country);
    }
  }
}
</script>

<style lang="css" scoped>
</style>
