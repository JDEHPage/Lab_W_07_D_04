<!-- <template lang="html">
  <li v-on:click="clickEvent">{{country.name}}</li>
</template>

<script>

import { eventBus } from '../main.js'

export default {
  name: 'list-item',
  props: ['country'],
  methods: {
    clickEvent(){
      eventBus.$emit('country-selected', this.country);
    }
  }
}
</script>

<style lang="css" scoped>
</style> -->
