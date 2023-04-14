<template>
  <div class="home">
  
    <CalcuLator></CalcuLator>
  </div>
</template>

<script>
// @ is an alias to /src
import CalcuLator from '../components/Calculator.vue'

export default {
  name: 'HomeView',
  components: {
    CalcuLator,
  }
}
</script>
