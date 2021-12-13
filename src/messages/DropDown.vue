<template>
  <div>
    <Dropdown
      v-model="selectedCity"
      :options="cities"
      option-label="name"
      placeholder="Select a City"
      @change="onSelection($event)"
    />
  </div>
</template>

<script>
import store, {mapState} from '../store'
import Dropdown from 'primevue/dropdown'

export default {
  components: {
    Dropdown
  },
  props: {
    onSubmit: {
      type: Function,
      required: true
    }
  },
  data() {
    return {
      selectedCity: null,
      cities: [
        {name: 'New York', code: 'NY'},
        {name: 'Rome', code: 'RM'},
        {name: 'London', code: 'LDN'},
        {name: 'Istanbul', code: 'IST'},
        {name: 'Paris', code: 'PRS'}
      ]
    }
  },
  computed: {},
  methods: {
    onSelection(event) {
      console.log(event)
      this.onSubmit({author: 'me', type: 'text', data: {text: 'test'}})
    }
  }
}
</script>

<style scoped lang="scss"></style>
