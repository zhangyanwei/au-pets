<template>
  <div id="app">
    <pets src="http://5c92dbfae7b1a00014078e61.mockapi.io/owners"/>
  </div>
</template>

<script>
import Pets from './components/Pets.vue'

export default {
  name: 'app',
  components: {
    Pets
  }
}
</script>
